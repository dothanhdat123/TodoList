<template>
    <div class="card panel-success">
        <div class="card-header">List Task</div>
        <table class="table table-hover ">
            <thead>
                <tr>
                    <th style="width: 10%" class="text-center">#</th>
                    <th>Task</th>
                    <th style="width: 20%" class="text-center">Level</th>
                    <th style="width: 160px">Action</th>
                </tr>
            </thead>

            <tbody >
                <todo-list-item 
                   v-for="(listTask, index) in listTasks" :key="listTask.id" :listTask= listTask :index="index"
                />
                <!-- <todo-list-item /> -->
                <!-- <todo-list-item /> -->
            </tbody>

            <tbody>
                <tr>
                    <td colspan="4"><h3>List Empty</h3></td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
import TodoListItem from './TodoListItem';

export default {
    name: 'todo-list-table',
    components: {
        TodoListItem
    },
    data() {
        return {
            
        }
    },
    props:{
        listTasks:{
           type: Object,
           required: true
         }
    },
    methods: {
    }
}
</script>

<style>

</style>
