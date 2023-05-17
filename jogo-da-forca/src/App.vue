<template>
  <div id="app">
    
    <h1>Jogo da Forca</h1>

    <section v-if="tela === 'inicio'" id="inicio">
      Início
    </section>

    <section v-if="tela === 'jogo'"  id="jogo">
      Jogo
    </section>

  </div>
</template>

<script>
import './css/global.css';

export default {
  name: 'App',
  data() {
    return {
      tela: 'inicio'
    }
  },
  components: {
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
