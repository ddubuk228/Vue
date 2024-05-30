
<template>
  <div id="app" class="container">
    <div class="card card-body bg-light">
      <div class="title">:: Todolist App</div>
    </div>

    <div clasee="card card-default card-borderless">
      <div class="card-bidy">
        <InputTodo />
        <TodoList :todoList="todoList" />
      </div>
    </div>
  </div>
</template>

<script>
  import TodoList from './components/TodoList.vue'
  import InputTodo from './components/InputTodo.vue'

  let ts = new Date().getTime()

  export default {
    name: "App",
    components: { InputTodo, TodoList},
    created() {
      this.emitter.on("add-todo", this.addTodo);
      this.emitter.on("delete-todo", this.deleteTodo);
      this.emitter.on("toggle-completed", this.toggleCompleted);
    },
    data() {
      return {
        todoList: [
          { id: ts, todo: "영화보기", completed: false},
          { id: ts+1, todo: "공부", completed: false},
          { id: ts+2, todo: "산책", completed: false},
          { id: ts+3, todo: "저녁 약속", completed: false},
        ]
      }
    },
    methods:{
      addTodo(todo) {
        if(todo.length >= 2) {
          this.todoList.push({id: new Date().getTime(), todo: todo, completed: false })
        }
      },
      deleteTodo(id){
        let index = this.todoList.findIndex((item) => id === item.id);
        this.todoList.splice(index, 1);
      },
      toggleCompleted(id){
        let index = this.todoList.findIndex((item) => id === item.id );
        this.todoList[index].completed = !this.todoList[index].completed;
      },
    }
  }
</script>

<style scoped>

</style>