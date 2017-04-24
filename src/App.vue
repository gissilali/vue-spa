<template>
  <div class="container">
    <div class="row">
      <div class="col-md-6 offset-3">
        <navbar></navbar>
        <todo-form v-bind:todos="todos"></todo-form>
      </div>
    </div>
    <div class="row">
    <div class="col-md-6 offset-3">
      <to-do-list v-bind:todos="todos" @todo-submitted="createTodo"></to-do-list>
    </div>
  </div>
  </div>
</template>

<script>
import ToDoList from './components/ToDoList'
import TodoForm from './components/TodoForm'
import Navbar from './components/Navbar'

export default {
  name: 'app',
  components: {
    ToDoList,
    TodoForm,
    Navbar
  },
  data () {
    return {
      todos: []
    }
  },
  methods: {
    createTodo () {
      alert('stuff is created')
    }
  }
}
</script>

