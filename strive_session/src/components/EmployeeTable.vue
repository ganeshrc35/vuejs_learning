<template>
	<div class="row">
		<div class="col-xs-12">
			<table class="table table-bordered">
				<thead>
					<tr>
						<th>Name</th>
						<th>Email</th>
					</tr>
				</thead>
				<tbody>
					<tr v-for="employee in employees" :key="employee.id">
						<td>{{employee.name}}</td>
						<td>{{employee.email}}</td>
					</tr>
				</tbody>
			</table>
		</div>
	</div>
</template>
<script>
	export default{
		name : 'employee-table',
		props:{
			employees:Array // Defining the type of data here.
		}
	}
</script>
<style scoped>

</style>