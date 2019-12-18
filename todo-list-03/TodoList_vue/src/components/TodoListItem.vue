<template>
    <tr>
        <td class="text-center">{{ index}}</td>
        <td>{{ listTask.taskName}}</td>
        <td class="text-center">
            <span class="badge" :class="classObjdect">{{getLevelName}}</span>
        </td>
        <td>
            <button 
                type="button" class="btn btn-warning">Edit</button>
            <button 
                type="button" class="btn btn-danger">Delete</button>
        </td>
    </tr>
</template>

<script>
export default {
    name: 'todo-list-item',
    data:{
       return:{
           
       }
    },
    props:{
        listTask:{
            type: Object,
            required: true
        },
        index: Number
    },
    computed:{
        getLevelName(){
            switch(this.listTask.level){
                case 0: 
                  return "Small"
                case 1: 
                  return "Normal"
                case 2: 
                  return "Hight"
                default: 
                  break;
            }
        },
        classObjdect: function(){
            return{
                'small': this.listTask.level == 0,
                'normal': this.listTask.level == 1,
                'hight' : this.listTask.level == 2
            }
        }
    }
   
}
</script>

<style scoped>
   .small{
       color: cadetblue;
   }
   .normal{
       color: blue;
   }
   .hight{
       color: darkred;
   }
</style>
