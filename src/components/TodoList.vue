<template>
  <div class="container">
    <h2 class="">My Todo List</h2>
    <div class="card">
      <div class="card-inner">
        <ul class="list-group">
          <li class="list-group-item d-flex p-3" v-for="(todo, index) in todos" :key="index">
            <div class="flex-fill">{{ todo | capitalize }}</div>
            <div class="list-item-delete">
              <button type="button" @click="removeTodo(index)" class="btn btn-danger" title="Delete">X</button>
            </div>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
import { mapState, mapActions } from 'vuex';
export default {
  name: "TodoList",
  filters: {
    capitalize(value) {
      if (!value) return '';
      return value.charAt(0).toUpperCase() + value.slice(1);
    }
  },
  computed: {
    ...mapState(['todos']),
  },
  methods: {
    ...mapActions(['removeTodo']),
  },
};
</script>
