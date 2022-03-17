<template>
  <h1>Reaction Timer</h1>
  <button @click="start" :disabled="isPlaying" >play</button>
  <BlockVue v-if="isPlaying" :delay="delay" />
</template>

<script>
import BlockVue from "./components/Block.vue"
export default {
  name:'App' ,
  data () {
    return {
      isPlaying: false,
      delay: null
    }
  },
  methods: {
    start() {
      this.delay = 1000 + Math.random() * 3000
      this.isPlaying = true
    }
  },
  components: {BlockVue}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #444;
  margin-top: 60px;
}
</style>