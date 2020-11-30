<template>
  <div>
    <p>HELLO COUNTER</p>
    <div>{{ count }}</div>
    <button v-on:click="countMaker">TOUCH MY TA-LA-LA</button>
  </div>
</template>

<script>
export default {
  name: "CountMaker",
  data: function () {
    return {count: 5}
  },
  methods: {
    countMaker() {
// eslint-disable-next-line no-debugger
      debugger
      return this.count++
    }
  }

}
</script>

<style scoped>

</style>
