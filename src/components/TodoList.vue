<template>
  <div
    class="
      flex flex-col
      mx-auto
      relative
      z-10
      mt-5
      w-1/3
      bg-slate-700
      shadow-xl
      rounded-lg
      px-4
      py-2
      text-white
    "
  >
    <p class="text-sm text-slate-400 py-2 border-b-2 border-slate-500">
      <span class="text-sky-400">{{ todosLen }}</span> Items Left
    </p>
    <ul
      class="divide-y w-full divide-slate-500 mt-1"
      v-bind:key="todo.id"
      v-for="todo in todos"
    >
      <Todo v-bind:todo="todo" v-on:del-todo="$emit('del-todo', todo.id)" />
    </ul>
  </div>
</template>

<script>
import Todo from "./Todo.vue";
export default {
  name: "TodoList",
  components: {
    Todo,
  },
  data() {
    return {
      todosLen: this.todos.length,
    };
  },
  props: ["todos"],
  watch: {
    todos: {
      handler(newVal, __oldVal) {
        this.todosLen = newVal.length;
      },
      deep: true,
      immediate: true,
    },
  },
};
</script>

