<template>


  <form @submit.prevent="onSubmit">
    <input type="text" v-model="title">

    <button type="submit">ADD TODO</button>
  </form>

</template>

<script>
export default {
  name: "AddTodo",
  data() {
    return {
      title: ''
    }
  },
  methods: {
    onSubmit() {
      this.$emit('create-todo', this.title)
      this.title = ''
    }

  }

}
</script>

<style scoped>

</style>
