<template>
  <div class="forca">

    <img :src="`https://raw.githubusercontent.com/william-costa/wdev-hangman-game-resources/master/images/hangman/${ erros }.svg`">

  </div>
</template>

<script>
export default {
  name: 'Forca',
  props: {
    erros: Number
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

  .forca img {
    width: 20%;
  }
  

</style>
