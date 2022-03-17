<template>
  <p>Reaction Time: {{ score }} ms</p>
  <p class="rank"> {{ rank }}  </p>
</template>

<script>
export default {
  name:'Results' ,
  data () {
    return {
      rank: null
    }
  },
  props: {
    score: Number,
  },
  mounted() {
    if( this.score < 250 ) {  
      this.rank = 'Ninja Fingers'
    } else if ( this.score < 400 ){
      this.rank = 'Rapid Reflexes'
    } else {
      this.rank = 'Snail Pace...'
    }
  }
}
</script>

<style>
  .rank {
    font-size: 1.4em;
    color: aquamarine;
    font-weight: bold;
  }
</style>