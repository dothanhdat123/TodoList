<template>
    <div class="form-group add-task">
        <button 
        v-if="!isForm"
         v-on:click="openForm"
            type="button" class="btn btn-info btn-block">Add Task</button>
        <button 
        v-else
         v-on:click="openForm"
            type="button" class="btn btn-primary btn-block">Close Form</button>
     </div>
</template>

<script>
export default {
    name: 'form-add',
    data() {
        return {
           isAddTask: false
        }
    },
     props:{
       isForm:{
           type: Boolean,
           default:false
       }  
    },
    methods: {
        openForm(){
            console.log("open form FormAdd");
            this.$emit("openForm");
            
        }
    }
}
</script>

<style>

</style>
