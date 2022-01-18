<template>
 <h1>Ninja Reaction Timer</h1>
 <button @click="start" :disabled="isPlaying">Play</button>
 <Block v-if="isPlaying" :delay="delay" @end="endGame"/>
<Results v-if="showResults" :score = "score"/>
</template>

<script>
import Block from './components/Block.vue'
import Results from './components/Results.vue'

export default {
  name: 'App',
  components: { Block, Results},
  data() {
    return{
      isPlaying: false,
      delay: null,
      score: null,
      showResults: false
    }
  },
  methods: {
    start(){
      this.delay = 2000 + Math.random() * 2000
      this.isPlaying = true
      this.showResults = false
    },
    endGame(reactionTime) {
      this.score = reactionTime
      this.isPlaying = false
      this.showResults = true
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
button {
  background: rgb(66, 199, 86);
  color: aliceblue;
  border: none;
  border-radius: 5px;
  padding: 5px 10px;
  font-size: 25px;
  letter-spacing: 2px;
  cursor: pointer;
  margin: 10px;
}
button[disabled] {
  opacity: 0.2;
  cursor:not-allowed;
}
</style>
