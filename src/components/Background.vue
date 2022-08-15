<script>
export default {
  name: 'Background'
}
</script>

<template>
    <div 
    class="h-64 w-screen"
    >
        <img 
            src="https://images.unsplash.com/photo-1660489055865-e075801b0557?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1475&q=80"
            alt="Iceland Valley"
            class="h-full w-full object-cover object-center"
        >
        <div 
        class="absolute h-64 w-full top-0 left-0 bg-gradient-to-r from-red-400 to-violet-600 opacity-50"
        ></div>
    </div>
</template>