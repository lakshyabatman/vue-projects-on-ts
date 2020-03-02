<template>
  <div class="home">
    <p>Todo using Typescript + Vue </p>
    <InputTodo :AddTodo="this.addTodo"/>
    <TodoList :todos="this.todos"/>
  </div>
</template>

<script>
import TodoList from '@/components/TodoList'
import InputTodo from '@/components/InputTodo'
// @ is an alias to /src
import {Vue,Component} from 'vue-property-decorator'

@Component({
  name:'Todo',
  components:{
    TodoList,
    InputTodo,
    
  }
})
export default class Todo extends Vue {
  todos= []
  addTodo (currentTodo) {
    if(currentTodo==="") {
      alert("Todo should not be empty")
      return 0;
    }
    this.todos.push(currentTodo);
  }
}
</script>
