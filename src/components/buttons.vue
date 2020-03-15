<template>
  <div>
    <input
      class="todoinput"
      type="text"
      placeholder="Enter new TODO"
      v-model="newTodo"
      @keypress.enter="addTodo(newTodo)"
    />
    <button @click="addTodo(newTodo)">ADD</button>
    <div v-for="(todo, index) in todos" :key="index" class="todoitem">
      <div>{{ todo }}</div>
      <div class="removeitem" @click="removeTodo(index)">&times;</div>
    </div>
    <template v-if="todos.length == 0">
      <h3>
        No Todos
      </h3>
    </template>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newTOdo: " ",
      todos: []
    };
  },
  methods: {
    addTodo(todo) {
      this.todos.push(todo);
      this.newTodo = "";
    },
    removeTodo(index) {
      this.todos.splice(index, 1);
    }
  }
};
</script>
<style lang="scss">
.todoinput {
  width: 50%;
  padding: 5px 5px;
  font-size: 18px;
  margin-bottom: 10px;
  &:focus {
    outline: 0;
  }
}
.todoitem {
  margin-bottom: 10px;
  padding: 10px 10px;
  display: flex;
  justify-content: space-around;
}
.removeitem {
  cursor: pointer;
  margin-right: 14px;
  &:hover {
    color: black;
  }
}
</style>
