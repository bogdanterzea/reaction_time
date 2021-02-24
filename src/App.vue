<template>
  <div @click="retardedDetected">
    <h1>Reacton Timer</h1>
    <button @click="start" :disabled="isPlaying">PLAY!</button>
    <Block v-if="isPlaying" :delay="delay" @endGame="endGame"/>
    <Results v-if="showResults" :score="score"/>
  </div>
</template>

<script>
import Block from './components/Block.vue'
import Results from './components/Results.vue'


export default {
  components: { Block, Results },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResults: false
    }
  },
  name: 'App',
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true
      this.showResults = false
    },
    endGame(reactionTime) {
      this.score = reactionTime
      this.isPlaying = false
      console.log(this.score);
      this.showResults = true
    },
    retardedDetected() {
      if(this.isPlaying) {
        this.start()
      }
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ff3333;
  margin-top: 60px;
}
</style>
