<template>
	<div id="app">
		<b-container>
			<comp-title />
			<b-row>
				<comp-control
				 v-bind:strSearch = strSearch
				 v-on:handleSearch = handleSearch
				/>
				<comp-form 
				/>
			</b-row>
			<todo-list-table 
		        v-bind:listTasks = listTasks
			/>
		</b-container>
	</div>
</template>

<script>

import TodoListTable from './components/TodoListTable';
import CompTitle from './components/CompTitle';
import CompControl from './components/CompControl';
import CompForm from './components/CompForm';

import listTask from './mocks/tasks';

export default {
	name: 'app',
	components: {
		CompForm,
		CompTitle,
		CompControl,
		TodoListTable
	},
	data(){
        return{
			strSearch: '',
			listTasks: [
				{
					id:1,
					taskName:"this is task 1",
					level: 0
				},
				{
					id:2,
					taskName:"this is task 2",
					level: 2
				},
				{
					id:3,
					taskName:"this is task 3",
					level: 1
				}
			]
		}
	},
	methods:{
		handleSearch(data){
		this.strSearch = data;
		        console.log("controller app.vue");
		},
		
	}
}
</script>

<style>
body {
    padding: 100px 0;
}
.table>tbody>tr>td, .table>tbody>tr>th, .table>tfoot>tr>td, .table>tfoot>tr>th, .table>thead>tr>td, .table>thead>tr>th {
    vertical-align: middle;
}

.container > .row {
    margin-top: 20px;
    margin-bottom: 30px;
}

span.badge-medium {
	padding: 11px 10px;
    margin: 0px 8px;
    font-size: 16px;
    display: inline-block;
    vertical-align: top;
}

@media (max-width: 992px) {
    .add-task {
        margin-top: 50px;
    }
}

</style>
