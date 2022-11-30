<script>
//import AppName  from './....AppName.vue'
import {store} from "../store";
import axios from "axios";


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
        performSearch(searchText, category){
            if(category === 'film'){
                axios.get("https://api.themoviedb.org/3/search/movie?api_key=855b32a225edd597704e4c0ca5c50972&language=en-US&page=1&include_adult=false&query="+searchText) 
                .then((resp) => {
                this.store.film = resp.data.results;
                })
            } else {
                axios.get("https://api.themoviedb.org/3/search/tv?api_key=855b32a225edd597704e4c0ca5c50972&language=en-US&page=1&include_adult=false&query="+searchText) 
                .then((resp) => {
                this.store.serieTv = resp.data.results;
                })

            }
        },
    }


}
</script>

<template>
    <div class="search-bar">
        <input type="search" placeholder="Search Films or Series" v-model="store.searchText">
        <div class="select">
            <select v-model="store.category" name="films or series" id="category" form="carform">
                <option value="Film">Film</option>
                <option value="Serie">Serie</option>
            </select>
        </div>
        <button @click="performSearch(this.store.searchText, this.store.category)" class="search-btn">Cerca</button>
        <ul></ul>
    </div>
    <!-- <AppName/> -->
</template>

<style scoped>

</style>
