<script>
import Background from "./components/Background.vue";
import Input from "./components/Input.vue";
import TodoList from "./components/TodoList.vue";

export default {
  name: "App",
  components: {
    Background,
    Input,
    TodoList,
  },
  data() {
    return {
      todos: [],
      filteredTodos: []
    };
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter((todo) => todo.id !== id);
    },
    addTodo(todo) {
      const { title, complated } = todo;

      this.todos.push({
        id: Math.random(),
        title: title,
        complated: complated,
      });
    },
    complateTodo(id) {
      this.todos = this.todos.map((todo) => {
        if (todo.id === id) {
          todo.complated = !todo.complated;
        }
        return todo;
      });
    },
    changeFilter(filter) {
        if (filter == 'all') {
          this.filteredTodos = this.todos;
        } else if (filter == 'active') {
          this.filteredTodos = this.todos.filter(todo => !todo.complated);
        } else if (filter == 'complated') {
          this.filteredTodos = this.todos.filter(todo => todo.complated);
        }
    }
  },
};
</script>

<template>
  <div class="overflow-x-hidden">
    <Background />
    <Input v-on:addTodo="addTodo" />
    <TodoList v-bind:todos="todos" v-on:del-todo="deleteTodo" v-on:filterTodo="changeFilter"/>
  </div>
</template>
