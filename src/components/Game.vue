<template>
  <section class="game-components">
    <div id="body">
      <Header/>






    </div>

  </section>
</template>

<script>

  import Header from './Header.vue'

  export default {
    name: 'game-components',
    props: [],
    components : {
      Header
    }
  }
</script>


<style scoped>
  .game-components {
    background: #232323;
  }
  #body {
    background: #232323;
    margin: 0;
    font-family: "Montserrat", "Avenir";
  }

</style>
