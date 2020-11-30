<template>
  <div id="app">
    <router-link to="/">HOME</router-link>
    <!--    <HelloWorld msg="Welcome to Your Vue.js App"/>-->
    <CountMaker/>

    <Todolists/>
    <button v-on="getTodoloists">GET TODOLISTS</button>
  </div>
</template>

<script>

import CountMaker from "@/components/CountMaker";
import Todolists from "@/components/Todolists";


export default {
  name: 'App',
  data() {
    return {
      todos: [
        // {id: 1, name: 'todo1', selected: false},
        // // {id: 2, name: 'todo2', selected: true},
        // {id: 3, name: 'todo3', selected: false},
        // {id: 4, name: 'todo4', selected: false}
      ],
      todoName: null
    }
  },
  components: {
    Todolists,
    CountMaker
  },
  mounted() {

  },

  methods: {},

}

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
