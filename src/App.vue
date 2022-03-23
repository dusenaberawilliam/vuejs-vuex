<template>
  <div id="app" class="todo">
    <h1>Todo app</h1>
    <AddTodo />
    <Todo />
  </div>
</template>

<script>
import Todo from "./components/Todo.vue";
import AddTodo from "./components/AddTodo.vue";
export default {
  name: "App",
  components: { Todo, AddTodo },
};
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 60px;
}
.todo {
  width: 90%;
  margin: 0 auto;
}
</style>
