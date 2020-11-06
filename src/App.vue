<template>
  <div class="todo-container">
    <div class="todo-wrap">
      <TodoHeader :addTodo="addTodo"/>
      <TodoList :todos="todos"/>
      <TodoFooter/>
    </div>
  </div>
</template>

<script>
  import TodoFooter from "./components/TodoFooter";
  import TodoHeader from "./components/TodoHeader";
  import TodoList from "./components/TodoList";

  export default {

    data() {
      return {
        todos: [
          {title: '吃饭', complete: false},
          {title: '睡觉', complete: false},
          {title: '打豆豆', complete: false}
        ]
      }
    },
    methods: {
      addTodo(todo){
        //unshift() 方法可向数组的开头添加一个或更多元素，并返回新的长度
        this.todos.unshift(todo)
      }
    },


    components: {
      TodoList,
      TodoHeader,
      TodoFooter
    }
  }
</script>

<style>
  /*app*/
  .todo-container {
    width: 600px;
    margin: 0 auto;
  }

  .todo-container .todo-wrap {
    padding: 10px;
    border: 1px solid #ddd;
    border-radius: 5px;
  }

</style>
