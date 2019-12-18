<template>
    <div class="col-12">
        <div class="input-group">
            <input 
                v-bind:value="strSearch"
                v-on:input = "handleSearch"
                type="text" class="form-control"  placeholder="Search for..." />
                <span class="input-group-append">
                <button 
                v-on:click="handleClearSearch"
                    class="btn btn-info" type="button">Clear!</button>
            </span>
        </div>
    </div>
</template>

<script>
// v-model => v-bind -> v-on:input
export default {
    name: 'control-search',
    data() {
        return { 

        }
    },
     props:{
        strSearch:{
            type: String,
            default: ''
        }
    },
    methods: {
       handleSearch(e){
        //    this.$emit("handleSearch",e.target.value);
        // this.strSearch = e.target.value;
        this.$emit("handleSearch",e.target.value);
        console.log("controller search.vue");
       },
       handleClearSearch(){
           this.$emit("handleSearch", "");
       }
    }
}
</script>

<style>

</style>
