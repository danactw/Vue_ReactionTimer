<template>
  <div class="block">
    Click me
  </div>
</template>

<script>
export default {
  name:'Block' ,
  data () {
    return {

    }
  },
  methods: {

  },
  props: {
    delay: Number,
  },
  components: {

  },
  emits: ['']
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