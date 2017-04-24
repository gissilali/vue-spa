<template>
	<div class="form-horizontal">
		<h4 class="text-info">Add Stuff</h4>
		<div class="form-group">
				<button type="submit" class="btn btn-success fa fa-edit" @click="showForm"></button>
		</div>
		<transition name="slide">
			<div v-if=isCreating>
			<form action="index.html"  @submit.prevent="submitToDo">
			<div class="alert-dismissible alert alert-danger" v-if=error>
				Error in your form
			</div>
			<div class="form-group">
				<input type="text" class="form-control" v-model="titleText"  @keyup="clearError">
			</div>
			<div class="form-group">
				<textarea name="" id="" cols="30" rows="10" class="form-control" v-model="descriptionText" @keyup="clearError"></textarea>
			</div>
			<div class="form-group">
				<button type="submit" class="btn btn-success fa fa-plus"></button>
			</div>
			</form>
			</div>
		</transition>
	</div>
</template>
<script>
export default{
  props: ['isCreating', 'todos'],
  data () {
    return {
      titleText: '',
      descriptionText: '',
      error: false
    }
  },
  methods: {
    showForm () {
      if (this.isCreating) {
        this.isCreating = false
      } else {
        this.isCreating = true
      }
    },
    submitToDo () {
      if (this.titleText.length > 0 && this.descriptionText.length > 0) {
        this.createTodo()
      } else {
        this.error = true
      }
    },
    clearError () {
      this.error = false
    },
    createTodo () {
      console.log(this.todos)
      this.todos.push({
        title: this.titleText,
        description: this.descriptionText,
        done: false
      })
      this.todos.reverse()
      this.clearForm()
    },
    clearForm () {
      this.titleText = ''
      this.descriptionText = ''
    }
  }
}
</script>
<style type="text/css">
	.form-horizontal{
		padding-top:20px;
	}
	button[type='submit']{
		cursor: pointer;
	}
</style>

