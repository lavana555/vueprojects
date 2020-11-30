<template>
  <div>
    todolists
    <Preloader v-if="isFetching"/>
    <ul v-if="todos.length">
      <select v-model="selected">
        <option value="all">ALL</option>
        <option value="completed">Completed</option>
        <option value="not-completed">Not-completd</option>
      </select>
      <span>{{ selected }}</span>
      <TodoItem
          v-for="todo in filteredTodos"
          v-bind:todo="todo"
          :key="todo.id"
          v-on:remove="removeTodo"
      />

    </ul>
    <p v-else>no todos</p>
    <AddTodo
        v-on:create-todo="cretTodolist"/>
  </div>
</template>


<script>
import AddTodo from "@/components/AddTodo";
import TodoItem from "@/components/TodoItem";
import Preloader from "@/components/Preloader";

export default {
  components: {
    AddTodo,
    TodoItem,
    Preloader
  },
  data() {
    return {
      todos: [],
      todoName: null,
      isFetching: true,
      selected: 'all'
    }
  },
  name: "Todolists",
  mounted() {
    fetch('https://jsonplaceholder.typicode.com/todos?_limit=10')
        .then(response => response.json())
        .then(json => {
          setTimeout(() => {
            this.todos = json
            this.isFetching = false
          }, 3000)

        })
  },
  computed: {
    filteredTodos() {
      var filter
      if (this.selected == 'all') {
        return filter = this.todos
      } else if (this.selected === 'completed') {
        return filter = this.todos.filter(todo => todo.completed === true)
      } else if (this.selected === 'not-completed') {
        return filter = this.todos.filter(todo => todo.completed === false)
      }
      return filter
    }

  },

  methods: {
    removeTodo(id) {
      console.log(id)
      this.todos = this.todos.filter((todo) => todo.id !== id)
    },
    cretTodolist(name) {
      let todonew = {
        id: Date.now(),
        title: name,
        selected: false
      }
      this.todos.push(todonew)
    }
  }
}
</script>

<style scoped>

</style>
