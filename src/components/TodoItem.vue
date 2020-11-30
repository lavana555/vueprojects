<template>
  <div id="todoitemList">
    <div id="item" >
    <span id="name">{{todo.title| upperCase}}</span>
    <strong v-bind:class="{done:todo.selected}">{{todo.id}}</strong>
    <input type="checkbox" value="todo.selected" v-on:change="todo.selected=!todo.selected"/>
    <button v-on:click="removeTodo">&times;</button>
    </div>
  </div>
</template>

<script>
export default {
name: "TodoItem",
  props:['todo'],
  methods:{
  removeTodo(){

    this.$emit('remove',this.todo.id)
  }
  },
  filters:{
  upperCase(value){
    return value.toUpperCase()
  }

  }

}


</script>

<style scoped>
#todoitemList{
  margin: 0 auto;
  margin-bottom: 15px;
  width: 450px;
  height: 150px;
  border: 1px solid goldenrod;
  border-radius: 50px;
  background-color: aqua;
}
#item{
  padding-top: 50px;

}
#name{
  font-size: 15px;
  padding-right: 70px;
}
button{
margin-left: 15px;
  border-radius: 15px;
  background-color: red;
}
.done{
text-decoration: red;
  font-size: 45px;
}
</style>
