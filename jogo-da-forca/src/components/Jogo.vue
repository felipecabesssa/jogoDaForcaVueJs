<template>
  <div class="jogo">

    <Forca :erros="erros" />

    <Palavra 
      :palavra="palavra"
      :dica="dica"
      :verificarLetra="verificarLetra"
      :etapa="etapa" 
    />

    <Teclado :letras="letras" :verificarLetra="verificarLetra"/>


  </div>
</template>

<script>

import Forca from './Forca.vue'
import Palavra from './Palavra.vue'
import Teclado from './Teclado.vue'

export default {

  components: { Forca, Palavra, Teclado },

  name: 'Jogo',

  props: {
    erros: Number,
    palavra: String,
    dica: String,
    verificarLetra: Function,
    etapa: String,
    letras: Array
  },

  data() {
    return {
      
    }
  },

  methods: {
    onSubmit: function() {
      
    }
  }
}
</script>

<style>

  .jogo {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
  }

</style>
