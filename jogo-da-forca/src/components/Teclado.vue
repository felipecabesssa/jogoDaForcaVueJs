<template>
  <div class="teclado">

    <button 
      class="teclado-botao" 
      v-for="(letra, key) in 'abcdefghijklmnopqrstuvwxyz'"
      :key="key"
      :disable="verificarLetra(letra)" 
    > 
      {{ letra }}
    </button>

  </div>
</template>

<script>
export default {
  name: 'Teclado',
  props: {
    letras: Array,
    verificarLetra: Function
  },
  data() {
    return {
      
    }
  },
  methods: {
    
  }
}
</script>

<style>

  .teclado {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    width: 90%;
    margin-top: 20px;
  }

  .teclado-botao {
    margin: 5px;
    text-transform: uppercase;
  }

</style>
