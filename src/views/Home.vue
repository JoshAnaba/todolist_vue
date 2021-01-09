<template>
  <div id="app">
    <AddTodo @add-todo="addTodo"/>
    <Todos :todos='todos' @del-todo="deleteTodo"/>
    <FilterSection 
    @show-all='showAll' 
    @show-active='showActive' 
    @show-completed='showCompleted' 
    @clear-completed='clearCompleted'/>
  </div>
</template>

<script>
import AddTodo from '../components/AddTodo';
import Todos from '../components/Todos';
import FilterSection from '../components/FilterSection';
// import {v4 as uuid} from 'uuid'
// import axios from 'axios';
export default {
  name: 'Home',
  components: {
    Todos,AddTodo,FilterSection
  },
  data(){
    return {

      todos: [
        {
          id: 1,
          title: 'Go to the mall',
          completed: false
        },
         {
          id: 2,
          title: 'Get foodstuff',
          completed: false
        },
         {
          id: 3,
          title: 'Get back home , cook and eat',
          completed: false
        }
       ]
    }
  },
  methods:{
    deleteTodo(id){
      this.todos = this.todos.filter(td=>td.id !== id)
    },
    addTodo(newTodo){
    
        this.todos =[...this.todos, newTodo]
    },

    showAll(){
      this.todos= this.todos.map(td=>td)
    },


    showActive(){
      this.todos = this.todos.filter(td=>td.completed == false)
    },

    showCompleted(){
        this.todos = this.todos.filter(td=>td.completed == true)
    },

    clearCompleted(){
      this.todos = this.todos.filter(td=>td.completed== false)
    }

  },


  // created(){
  //  axios.get('https://jsonplaceholder.typicode.com/todos?_limit=10')
  //  .then(res=>this.todos =[...this.todo, res.data.filter(re=>re.completed == false)])
  //  .catch(err => console.log(err))
  // }
}
</script>

<style lang='scss'>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
