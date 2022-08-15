<template>
  <li class="py-2">
    <div class="flex justify-between">
      <div class="flex gap-3 items-center">
        <input
          id="checkbox1"
          type="checkbox"
          class="peer w-4 h-4"
          v-on:change="markComplate"
          v-bind:checked="todo.complated"
        />
        <label
          for="checkbox1"
          class="peer-checked:line-through peer-checked:text-slate-300"
        >
          <p>{{ todo.title }}</p>
        </label>
      </div>
      <button @click="$emit('del-todo', todo.id)">
        <i class="bx bx-trash" style="color: #dc3b3b"></i>
      </button>
    </div>
  </li>
</template>

<script>
export default {
  name: "Todo",
  props: ["todo"],
  methods: {
    markComplate() {
      this.todo.complated = !this.todo.complated;
    },
  },
};
</script>

