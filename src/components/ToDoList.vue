<template>
	<div class="list">
		<todo v-for="(todo, index) in todos" v-bind:todo="todo" v-bind:index="index"></todo>
	</div>
</template>
<script>
import Todo from './Todo'
export default{
  props: ['todos', 'isCreating', 'done'],
  components: {
    Todo
  }
}
</script>
<style>
	.list{
		padding-top:20px;
	}
</style>
