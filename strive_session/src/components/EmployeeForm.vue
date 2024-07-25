<template>
	<div class="row" id="employee-form">
		<div class="col-xs-12">
			<form v-on:submit.prevent="handleSubmit">
				<label class="form-label">Name</label>
				<input type="text" class="form-control" name="name" v-model="employee.name"/>
				<label class="form-label">Email</label>
				<input type="email" class="form-control" name="email" v-model="employee.email"/>
				<input type="submit" class="btn btn-primary" value="Submit"/>
			</form>
		</div>
	</div>
</template>
<script>
	export default({
		name:'employee-form',
		data(){
			return {
				employee:{
					name:'',
					email:''
				}
			}
		},
		methods:{
			//Here we will be writting the functions. Here I am handling submit event listener method.
			handleSubmit(){
				this.$emit('add:employee',this.employee); //This will emit the event from employee vue component to app component with employee data
			}
		}
	})
</script>
<style scope>
</style>