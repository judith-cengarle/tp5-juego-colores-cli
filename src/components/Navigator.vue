<template>
    
    <div id="navigator">
        <button @click="onReset()">{{startGame}}</button>
        <span id="message">{{messageValue}}</span>
        <button id="easy" @click="onEasy" :class="{selected:(activeButton==='easy')}">easy</button>
        <button id="hard" @click="onHard" :class="{selected:(activeButton==='hard')}">hard</button>
    </div>   
  


</template>

<script>
    export default {
        name : 'game-components',
        props : {
           startGame : "",
           messageValue : ""
        },
        data : function() {
            return {
                activeButton : "hard"
            };  
        },
        methods : {
            onReset : function() {
                this.$emit("onResetClick");
            },
            onEasy : function() {
                this.$emit("onEasyClick");
                this.activeButton = "easy";
            },
            onHard : function() {
                this.$emit("onHardClick");
                this.activeButton = "hard";
            }
        }
    }
</script>

<style scoped>
  
    #navigator { 
        background: #ffffff;
        height: 30px;
        text-align: center;
        margin: 0;
        margin-top: -30px;
    }
    #message {
        color: black;
        display: inline-block;
        width: 20%;
    }
    .selected {
        background-color: steelblue;
        color: white;
    }
    button {
        border: none;
        background-color: white;
        font-family: "Montserrat", "Avenir";
        text-transform: uppercase;
        height: 100%;
        font-weight: 700;
        letter-spacing: 1px;
        color: steelblue;
        transition: all 0.3s;
        outline: none;
    }
    button:hover {
        color: white;
        background-color: steelblue;
    }
</style>