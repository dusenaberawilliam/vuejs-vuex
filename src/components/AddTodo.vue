<template>
  <div>
    <form @submit="onSubmit">
      <h4>Add todo</h4>
      <input type="text" placeholder="Enter todo Name" v-model="title" />
      <button type="submit">Add</button>
    </form>
  </div>
</template>

<script>
import { mapActions } from "vuex";

export default {
  name: "AddTodo",
  data() {
    return {
      title: "",
    };
  },
  methods: {
    ...mapActions(["addTodo"]),
    onSubmit(e) {
      e.preventDefault();
      this.addTodo(this.title);
    },
  },
};
</script>

<style scoped>
input {
  padding: 10px;
}
button {
  padding: 10px;
}
</style>