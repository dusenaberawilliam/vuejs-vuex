<template>
  <div>
    <div class="todo">
      <div
        @dblclick="onDblClick(todo)"
        v-for="(todo, index) in getTodos"
        :key="index"
        class="all_todo"
      >
        <p>Title: {{ todo.title }}</p>
        <p>completed: {{ todo.completed }}</p>
        <button @click="removeTodo(todo.id)">Delete</button>
      </div>
    </div>
  </div>
</template>

<script>
import { mapGetters, mapActions } from "vuex";
export default {
  name: "Todo",
  components: {},

  computed: mapGetters(["getTodos"]),
  methods: {
    ...mapActions(["fetchTodos", "removeTodo", "updateTodo"]),
    onDblClick(todo) {
      const updTodo = {
        id: todo.id,
        title: todo.title,
        completed: !todo.completed,
      };
      this.updateTodo(updTodo);
    },
  },
  created() {
    this.fetchTodos();
  },
};
</script>

<style scoped>
.todo {
  display: flex;
  flex-wrap: wrap;
}
.all_todo {
  background: rgb(223, 223, 223);
  margin: 10px;
  padding: 0 10px 10px;
  border-radius: 3px;
}
</style>