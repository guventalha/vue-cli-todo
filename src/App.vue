<template>
  
  <AppHeader/>
  <div class="w-full sm:w-[400px] mx-auto px-2 py-24">
    <AddSection @add-todo="addTodo"/>
    <TodoList :todoList="todos" @remove-todo="deleteItem"/>
  </div>
</template>

<script>
import AppHeader from '@/components/AppHeader'
import AddSection from './components/AddSection.vue';
import TodoList from './components/TodoList.vue';

export default {
  name: 'App',
  components: {
    AppHeader,AddSection,TodoList
  },
  data(){
    return {

      todos:[
        { id: 1, title: "Learn Vue3 CLI", done: true },
        { id: 2, title: "Use component tree", done: true },
        { id: 3, title: "Use provide - inject", done: true },

      ]
    }
  },
  methods:{
    addTodo(todo){
      this.todos.push({id:new Date().getTime(),title:todo,done:false})
      console.log(this.todos)
    },
    deleteItem(todo){
      
      this.todos = this.todos.filter(item=>item !== todo)
    },
    checkTodo(todo){
      todo.done = !todo.done
    }
  },
  provide(){
    return {
      completeTodo : this.checkTodo
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  
}
</style>
