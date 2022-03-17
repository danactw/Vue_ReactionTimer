<template>
  <h1>Reaction Timer</h1>
  <button @click="start" :disabled="isPlaying" >play</button>
  <BlockVue v-if="isPlaying" :delay="delay" @end="endGame" />
  <ResultsVue :score="score" v-if="showResult" />
</template>

<script>
import BlockVue from "./components/Block.vue"
import ResultsVue from "./components/Results.vue"

export default {
  name:'App' ,
  data () {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResult: false
    }
  },
  methods: {
    start() {
      this.delay = 1000 + Math.random() * 3000
      this.isPlaying = true
      this.showResult = false
    },
    endGame(reactionTime) {
      this.score = reactionTime
      this.isPlaying = false
      this.showResult = true
    }
  },
  components: { BlockVue , ResultsVue}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #444;
  margin-top: 60px;
}
button {
  background-color: aquamarine;
  color: white;
  border: none;
  border-radius: 5px;
  padding: 8px 16px;
  font-size: 16px;
  letter-spacing: 1px;
  cursor: pointer;
  margin: 10px;
}
button[disabled] {
  opacity: 0.2;
  cursor: not-allowed;
}
</style>