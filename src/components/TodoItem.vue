<template>
  <div>
    <p>
      <input type="checkbox" v-on:change="markComplete" name="" id="" />
      {{ todo.title }}
      <button @click="$emit('del-todo', todo.id)" class="del">Delete</button>
    </p>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed;
    },
  },
};
</script>
