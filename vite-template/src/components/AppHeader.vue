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
            if(category === 'Film'){
                axios.get("https://api.themoviedb.org/3/search/movie?api_key=855b32a225edd597704e4c0ca5c50972&language=en-US&page=1&include_adult=false&query="+searchText) 
                .then((resp) => {
                this.store.film = resp.data.results;
                })
                //debug
                console.log(this.store.film);
            } else {
                axios.get("https://api.themoviedb.org/3/search/tv?api_key=855b32a225edd597704e4c0ca5c50972&language=en-US&page=1&include_adult=false&query="+searchText) 
                .then((resp) => {
                this.store.serieTv = resp.data.results;
                })
                //debug
                console.log(this.store.film);
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
        <ul v-if="this.store.category === 'Film'" v-for="film in store.film">
            <li >{{film.title}}</li>
            <li >{{film.original_title}}</li>
            <li >{{film.original_language}}</li>
            <li >{{film.vote_average}}</li>
        </ul>
        <ul v-else >
            <li v-for="serie in store.serieTv"></li>
        </ul>
    </div>
    <!-- <AppName/> -->
</template>

<style scoped>

</style>
