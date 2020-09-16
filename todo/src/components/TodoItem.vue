<template>
  <li>
    <span v-bind:class="{done: todo.completed}">
      <input type="checkbox" v-on:change="todo.completed = !todo.completed" />
      {{todo.title}}
    </span>
    <button v-on:click="$emit('remove-todo', todo.id)">&times;</button>
  </li>
</template>

<script>
export default {
  props: {
    todo: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scoped>
li {
  width: 500px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  padding-bottom: 5px;
  text-align: left;
}
input {
  margin-right: 15px;
}
.done {
  text-decoration: line-through;
}
</style>