<template>
  <div class="container">
    <h2 class="">My Todo List</h2>
    <div class="card">
      <div class="card-inner">
        <ul class="list-group">
          <li class="list-group-item d-flex p-3" v-for="(todo, index) in todos" :key="index">
            <div class="flex-fill">{{ capitalizeTodoTitle(todo) }}</div>
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
  computed: {
    ...mapState(['todos']),
    capitalizeTodoTitle(){
      return title => {
        if (!title) return '';
        return title.charAt(0).toUpperCase() + title.slice(1);
      }
    }
  },
  methods: {
    ...mapActions(['removeTodo']),
  },
};
</script>
