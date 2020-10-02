<template>
  <form @submit.prevent="onSubmit">
    <input type="text" v-model="title" />
    <button type="submit">Add</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      title: "",
    };
  },
  methods: {
    onSubmit() {
      if (this.title.trim()) {
        const newTodo = {
          id: Date.now(),
          title: this.title,
          complited: false,
        }

        this.$emit('add-todo', newTodo)
        this.title = ''
      }
    },
  },
};
</script>

<style scoped>
form {
  padding-bottom: 10px;
  margin-top: 25px;
  display: flex;
  justify-content: center;
}
input {
  width: 280px;
}
</style>