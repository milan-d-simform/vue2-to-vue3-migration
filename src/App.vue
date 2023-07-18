<template>
  <div id="app">
    <h1><center>To-Do App</center></h1>
    <hr />
    <AddTodo />
    <hr />
    <TodoList />
  </div>
</template>

<script>
import TodoList from "./components/TodoList.vue";
import AddTodo from "./components/AddTodo.vue";
export default {
  components: {TodoList, AddTodo},
};
</script>