<template>
  <div class="todo-item" :class="{'is-complete':todo.completed}">
    <p class="todo-name">
      <input type="checkbox" @change="markComplete" />
      {{todo.title}}
      <button @click="$emit('delTodo',todo.id)" class="delete">X</button>
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
    }
  }
};
</script>
<style scoped>
.is-complete {
  text-decoration: line-through;
}
.delete {
  background-color: red;
}
</style>
