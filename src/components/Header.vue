<template>
    
    <section class="game-components" >
    <div id="header">
      <h1>The Great <br>
      
      <br>
      Guessing Game</h1>
    </div>
  </section>

</template>

<script>
    export default {
        name: 'game-components',
        props: {

        }        
        
    }
</script>

<style scoped>
    #header {
    transition: all 0.3s;    
    text-transform: uppercase;
    text-align: center;
    margin: 0;
    color: white;	
    }
</style>