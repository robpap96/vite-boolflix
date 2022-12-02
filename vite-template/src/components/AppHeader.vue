<script>
//import AppName  from './....AppName.vue'
import {store} from "../store";


export default {
    name: 'AppHeader',
    components: {

    },
    defineProps :{
        //msg: String
    },
    data(){
        return {
            store,
        }
    },
    methods: {
 
    },


}
</script>

<template>
    <div class="search-bar">
        <form @submit.prevent="$emit('performSearch')">
            <input type="search" placeholder="Search Films or Series" v-model="store.searchText" required>
            <select v-model="store.category" name="films or series" id="category" form="carform" required>
                <option value="Film">Film</option>
                <option value="Serie">Serie</option>
            </select>
            <button type="submit" class="search-btn">Cerca</button>

        </form>
    </div>
</template>

<style scoped>

</style>
