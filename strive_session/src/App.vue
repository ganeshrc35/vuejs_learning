<template>
    <div class="container">
        <h1>Employees</h1>
        <employee-form @add:employee="addEmployee"/>
        <employee-table v-bind:employees="employees"/>
    </div>
</template>

<script>
//Import the component file here
import EmployeeTable from './components/EmployeeTable.vue'
import EmployeeForm from './components/EmployeeForm.vue'

export default {
    name: 'App', //Name of the component
    components: {
        EmployeeTable,
        EmployeeForm
    },
    data(){
        //Here we will be generating the data dynamically to the table.
        return{
            employees:[
                {
                    id:1,
                    name:'Shenbaga Ganesh',
                    email:'ganesh.kalirajan@onestrive.com'
                },
                {
                    id:2,
                    name:'Kuntal Patel',
                    email:'kuntal.patel@onestrive.com'
                },
                {
                    id:3,
                    name:'Sonal Dholariya',
                    email:'sonal.dholariya@onestrive.com'
                },
                {
                    id:4,
                    name:'Rahul Singh',
                    email:'rahul.singh@onestrive.com'
                },
                {
                    id:5,
                    name:'Shobiya Karthikeyan',
                    email:'shobiya.karthikeyan@onestrive.com'
                }
            ]
        }
    },
    methods:{
        addEmployee(employee){

            //this.employees = [...this.employees,employee]; - To show newly added employee

            //To add id to the new columns
            
            const lastId = this.employees.length>0?this.employees[this.employees.length-1].id:0
            
            //This will get the length of existing employees object and get the last id. If length is 0, then last id will be 0
            
            const id = lastId + 1;

            //Now add id object to newly added employee data

            const newEmployee = {...employee,id};

            this.employees = [...this.employees,newEmployee]; 
        }
    }
}
</script>

<style>
</style>
