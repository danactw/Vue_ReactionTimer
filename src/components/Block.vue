<template>
  <div class="block" v-if="showBlock" @click="stopTimer">
    Click me
  </div>
</template>

<script>
export default {
  name:'Block' ,
  data () {
    return {
      showBlock: false,
      timer: null,
      reactionTime: 0
    }
  },
  methods: {
    startTimer() {
      this.timer = setInterval(()=>{
        this.reactionTime += 10
      }, 10)
    },
    stopTimer() {
      clearInterval(this.timer)
      this.$emit('end', this.reactionTime)
    }
  },
  props: {
    delay: Number,
  },
  components: {

  },
  emits: [''],
  mounted() {
    setTimeout(() => {
      this.showBlock = true
      this.startTimer()
      console.log(this.delay);
    }, this.delay)
  }
}
</script>

<style>
  .block {
    width: 400px;
    border-radius: 20px;
    background-color: #0faf87;
    color: white;
    text-align: center;
    padding: 100px 0;
    margin: 40px auto;
  }
</style>