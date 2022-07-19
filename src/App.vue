<template>
  <h1> Shaamer's Reaction Timer</h1>
  <p> Press play, then click the green button ASAP!</p>
  <button @click="start" :disabled="isPlaying"> PLAY</button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame"/>
  <Results v-if="showResult" :score="score"/>
 </template>

<script>
import Block from './components/Block.vue'
import Results from './components/Results.vue'
export default {
  name: 'App',
  components: {Block, Results},
  data(){
    return{
      isPlaying: false,
      delay: null,
      score: null,
      showResult:false
    

    }
  },
  methods: {
    start() {
      this.isPlaying = true
      this.delay = 2000 + Math.random() * 3000
      this.showResult = false

    },
    endGame(rctntm){
      this.score = rctntm
      this.isPlaying = false
      this.showResult = true

    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444;
  margin-top: 60px;
  
}
body{
  background:lightgray;
}
button[disabled]{
  opacity: 0.2;
  cursor: not-allowed;
}
</style>
