<template>
  <div>
    <div v-for="todo in todos" :key="todo.id">
      <todoItem :todo="todo" @delTodo="$emit('delTodo',todo.id)" />
    </div>
  </div>
</template>
<script>
import TodoItem from "./todoItem.vue";
export default {
  name: "Todos",
  components: {
    TodoItem
  },
  props: ["todos"]
};
</script>
<style scoped>
</style>