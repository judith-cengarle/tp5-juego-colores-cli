<template>
  <section class="game-components">
    <div id="body">
      <Header :title="pickedColour" :colour="headerColour"/>
      <Navigator :startGame="gameButton" :messageValue="message" @onResetClick="reset()" @onEasyClick="modeGameEasy()" @onHardClick="modeGameHard()" />





    </div>

  </section>
</template>

<script>

  import Header from './Header.vue'
  import Navigator from './Navigator.vue'

  export default {
    name: 'game-components',
    props: [],
    components : {
      Header,
      Navigator
    },
    data() {
      return {
          colourCount : 6,
          colours : [],
          pickedColour : null,
          headerColour : "",
          gameButton : "new colours",
          message : ""
      }
    },
    mounted : function() {
        this.reset();
    },
    methods : {
      reset : function() {
          this.colours = this.createNewColours(this.colourCount);
          this.pickedColour = this.colours[this.pickColour()];
          this.headerColour = "steelblue";
          this.message = "";
      },
      createNewColours : function(numbers) { 
            var arr = [];
            for (var i = 0; i < numbers; i++) {
                arr.push(this.createRandomStringColour());
            }
            return arr;
      },
      createRandomStringColour : function() {
          var newColour = "rgb(" + this.randomInt() + ", " + this.randomInt() + ", " +
          this.randomInt() + ")";
          return newColour;
      },
      randomInt : function() {
          return Math.floor(Math.random() * 256);
      },
      pickColour : function() {
          var quantity;
            if (this.isHard) {
                quantity = 6;
            } else {
                quantity = 3;
            }
            return Math.floor(Math.random() * quantity );
      },
      modeGameEasy : function() {
          
          if (this.isHard === true) {
              this.colourCount = 3;
              this.isHard = false;
              this.reset();
          }
          
      },
      modeGameHard : function() {
        
          if (this.isHard === false) {
              this.colourCount = 6;
              this.isHard = true;
              this.reset();
          }
      }
    }
    
  }
</script>


<style>

  body {
    background: #232323;
    margin: 0;
    font-family: "Montserrat", "Avenir";
  }

</style>
