<template>
  <div id="app">
    
    <h1>Jogo da Forca</h1>

    <section v-if="tela === 'inicio'" id="inicio">
      
      <Formulario v-if="etapa === 'palavra'"
        title="Defina a palavra"
        button="Próximo"
        :action="setPalavra"
      />

      <Formulario v-if="etapa === 'dica'" 
        title="Defina a dica"
        button="Iniciar jogo ;)"
        :action="setDica"
      />

      

    </section>

    <section v-if="tela === 'jogo'"  id="jogo">
      
      <Jogo 
      
        :erros="erros" 
        :palavra="palavra"
        :dica="dica"
        :verificarLetra="verificarLetra"
        :etapa="etapa"
        :letras="letras"
        :jogar="jogar"
        :jogarNovamente="jogarNovamente"

      />

    </section>

  </div>
</template>

<script>
import Formulario from './components/Formulario.vue';
import Jogo from './components/Jogo.vue';
import './css/global.css';

export default {
  name: 'App',
  data() {
    return {
      tela: 'inicio',
      etapa: 'palavra',
      palavra: '',
      dica: '',
      erros: 0,
      letras: []
    }
  },
  components: {
    Formulario,
    Jogo
  },
 
    methods: {
    setPalavra: function(palavra) {
      this.palavra = palavra;
      this.etapa = 'dica';
    },

    setDica: function(dica) {
      this.dica = dica;
      this.tela = 'jogo';
      this.etapa = 'jogo';
    },

    verificarLetra: function(letra) {
      return this.letras.find(item => item.toLowerCase() === letra.toLowerCase());
    },

    jogar: function(letra) {
      //ADICIONA LETRA JOGADA
      this.letras.push(letra);

      //VALIDAR ERRO
      this.verificarErros(letra);
    },

    verificarErros: function(letra) {
      //ACERTO
      if (this.palavra.toLowerCase().indexOf(letra.toLowerCase()) >= 0) {
          return this.verificarAcertos();
      }
      
      //ERROS
      this.erros++;

      //ENFORCADO
      if(this.erros === 6) {
        this.etapa = 'enforcado'
      }

    },

    verificarAcertos: function() {
      let letrasUnicas = [...new Set(this.palavra.split(''))];
      if(letrasUnicas.length === (this.letras.length - this.erros)) {
        this.etapa = 'ganhador';
      }
    },

    jogarNovamente: function() {
      this.palavra = '';
      this.dica = '';
      this.erros = '';
      this.letras = [];
      this.tela = 'inicio';
      this.etapa = 'palavra';

    }

  }
}
</script>

<style>
#app {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
</style>
