<template>
  <div class="container">
    <h2 class="">Add Todo</h2>
    <div class="card">
      <div class="d-flex">
        <input class="form-control" placeholder="Add new todo" v-model="newTodo"/>
          <button type="button" class="btn btn-primary" @click="addNewTodo">Add</button>
      </div>
    </div>
  </div>
</template>

<script>
import { mapActions } from 'vuex';
export default {
  name: "AddTodo",
  data() {
    return {
      newTodo: "",
    };
  },
  methods: {
    ...mapActions(['addTodo']),
    addNewTodo() {
      this.addTodo(this.newTodo);
      this.newTodo = "";
    },
  },
};
</script>
