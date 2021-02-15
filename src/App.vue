<template>
  <h1>Reacton Timer</h1>
  <button @click="start">PLAY!</button>
</template>

<script>
export default {
  data() {
    return {
      isPlaying: false,
      delay: null
    }
  },
  name: 'App',
  components: {
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true
      console.log(this.delay)
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
