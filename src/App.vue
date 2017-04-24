<template>
  <div class="container">
    <div class="row">
      <div class="col-md-6 offset-3">
        <todo-form v-bind:isCreating="isCreating" v-bind:todos="todos"></todo-form>
      </div>
    </div>
    <div class="row">
    <div class="col-md-6 offset-3">
      <to-do-list v-bind:todos="todos" v-bind:done="done" @todo-submitted="createTodo" v-bind="createTodo"></to-do-list>
    </div>
  </div>
  </div>
</template>

<script>
import ToDoList from './components/ToDoList'
import TodoForm from './components/TodoForm'

export default {
  name: 'app',
  components: {
    ToDoList,
    TodoForm
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

