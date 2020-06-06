<template>
  <section class="game-components">
    <div id="body">
      <Header :title="pickedColour"/>






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
    },
    data() {
      return {
          colourCount : 6,
          colours : [],
          pickedColour : null
      }
    },
    mounted : function() {
        this.reset();
    },
    methods : {
      reset : function() {
          this.colours = this.createNewColours(this.colourCount);
          this.pickedColour = this.colours[this.pickColour()];
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
      }
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
