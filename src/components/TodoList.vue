<template>
  <ul class="todo-main">

    <TodoIten v-for="(todo, index) in todos" :key="index" :todo="todo" :index="index"/>

  </ul>
</template>

<script>
    import TodoIten from "./TodoIten";
    export default {
      components: {TodoIten},
      props:{
           todos:Array
         }
    }
</script>

<style scoped>


  /*main*/
  .todo-main {
    margin-left: 0px;
    border: 1px solid #ddd;
    border-radius: 2px;
    padding: 0px;
  }

  .todo-empty {
    height: 40px;
    line-height: 40px;
    border: 1px solid #ddd;
    border-radius: 2px;
    padding-left: 5px;
    margin-top: 10px;
  }


</style>
