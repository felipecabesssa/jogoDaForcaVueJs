<template>
  <div class="jogo">

    <Forca :erros="erros" />

    <Palavra 
      :palavra="palavra"
      :dica="dica"
      :verificarLetra="verificarLetra" />

  </div>
</template>

<script>
import Forca from './Forca.vue'
import Palavra from './Palavra.vue'
export default {
  components: { Forca, Palavra },
  name: 'Jogo',
  props: {
    erros: Number,
    palavra: String,
    dica: String,
    verificarLetra: Function
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
