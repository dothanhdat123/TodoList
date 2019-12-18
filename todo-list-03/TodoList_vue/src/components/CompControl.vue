<template>
    <div class="col-12 col-lg-6">
        <div class="row">
            <!-- SORT : START -->
            <control-sort 
            />
            <!-- SORT : END -->

            <!-- SEARCH : START -->
            <control-search 
              v-bind:strSearch = strSearch
              v-on:handleSearch = handleSearch
              
            />
            <!-- SEARCH : END -->
        </div>
    </div>
</template>

<script>
import ControlSort from './ControlSort';
import ControlSearch from './ControlSearch';

export default {
    name: 'comp-control',
    components: {
        ControlSort,
        ControlSearch
    },

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
        handleSearch(data){
                // this.strSearch = e.target.value;
             this.$emit("handleSearch", data);
                     console.log("controller compController.vue");
        },   
    }
}
</script>

<style>

</style>
