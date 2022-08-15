<template>
  <div class="-mt-36 z-10 relative w-1/3 flex flex-col mx-auto">
    <h1 class="text-3xl font-bold text-white">To-Do</h1>
    <form @submit.prevent="addTodo"  class="w-full p-3 bg-slate-700 shadow-xl rounded-lg flex items-center">
      <button type="submit">
        <i class="bx bx-plus-circle bx-rotate-90 text-2xl mr-3 text-white"></i>
      </button>
      <input
        v-model="title"
        type="text"
        placeholder="Add your to-do"
        class="
          bg-transparent
          text-gray-300
          placeholder:text-white-500
          h-8
          outline-none
        "
      /> 
    </form>
  </div>
</template>

<script>
export default {
  name: "Input",
  data() {
    return {
      title: '',
    }
  },
  methods: {
    addTodo() {
      if(this.title == '') {
        return;
      }

      const newTodo = {
        title: this.title,
        complated: false
      }

      this.$emit('addTodo', newTodo);

      this.title = '';
    }
  }
};
</script>

