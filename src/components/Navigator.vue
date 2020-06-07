<template>
    
    <section class="game-components">
        <div id="navigator">
            <button @click="onReset()">{{startGame}}</button>
            <span id="message">{{messageValue}}</span>
            <button id="easy" @click="onEasy" :class="{selected:(activeButton==='easy')}">easy</button>
            <button id="hard" @click="onHard" :class="{selected:(activeButton==='hard')}">hard</button>
        </div>   
    </section>


</template>

<script>
    export default {
        name : "game-components",
        
    }
</script>

<style scoped>

</style>