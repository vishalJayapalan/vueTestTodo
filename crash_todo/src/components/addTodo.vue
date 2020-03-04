<template>
  <div>
    <input
      type="text"
      @keyup.enter="addTodo"
      v-model="title"
      name="title"
      placeholder="add todo..."
    />
  </div>
</template>
<script>
export default {
  name: "AddTodo",
  data() {
    return {
      title: ""
    };
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
      const newTodo = {
        title: this.title,
        completed: false
      };
      this.$emit("add-Todo", newTodo);
      this.title = "";
    }
  }
};
</script>