<template>
  <div id="app">
    <AddTodo v-on:add-todo="addTodo" />
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
import Todos from "./components/Todos.vue";
import AddTodo from "./components/AddTodo";

export default {
  name: "myApp",
  components: {
    Todos,
    AddTodo,
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "todo 1",
          completed: false,
        },
        {
          id: 2,
          title: "todo 2",
          completed: false,
        },
        {
          id: 3,
          title: "todo 3",
          completed: false,
        },
        {
          id: 4,
          title: "todo 4",
          completed: false,
        },
        {
          id: 5,
          title: "todo 5",
          completed: false,
        },
      ],
    };
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter((todo) => todo.id !== id);
    },
    addTodo(newTodo) {
      this.todos = [...this.todos, newTodo];
    },
  },
};
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
