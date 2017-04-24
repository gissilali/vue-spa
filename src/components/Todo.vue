<template>
	<div class="card form-group">
			<span class="label">{{ todo.id }}</span>
			<div class="card-header">{{ todo.title }}</div>
			<div class="card-block">{{ todo.description }}</div>
			<div class="card-footer">
				<button v-if="todo.done" class="btn btn-success fa fa-check"></button>
				<button v-else="todo.done" @click="isDone">Done</button>
			</div>
	</div>	
</template>
<script>
export default {
  props: ['todo'],
  methods: {
    isDone () {
      this.todo.done = true
    }
  }
}
</script>
