<template> 
    
  <section class="game-components" >
    <div id="header" :style="{backgroundColor:colour}">
      <h1>The Great<br>
          <span id="colourDisplay">{{title}}</span>
      <br>
      Guessing Game</h1>
    </div>
  </section>

</template>

<script>
    export default {
        name: 'game-components',
        props: {
          title : String,
          colour : String
        }        
        
    }
</script>

<style scoped>
  h1 {
    font-weight: normal;
    line-height: 1.1;
    padding: 20px 0;
  }
  #header {
    transition: all 0.3s;    
    text-transform: uppercase;
    text-align: center;
    margin: 0;
    color: white;	
  }
  #colourDisplay {
    font-size: 350%;
  }
</style>