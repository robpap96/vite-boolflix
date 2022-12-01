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
        // performSearch(searchText, category){
        //     if(category === 'Film'){
        //         axios.get("https://api.themoviedb.org/3/search/movie?api_key=855b32a225edd597704e4c0ca5c50972&language=en-US&page=1&include_adult=false&query="+searchText) 
        //         .then((resp) => {
        //         this.store.film = resp.data.results;
        //         })
        //         //debug
        //         console.log(this.store.film);
        //     } else {
        //         axios.get("https://api.themoviedb.org/3/search/tv?api_key=855b32a225edd597704e4c0ca5c50972&language=en-US&page=1&include_adult=false&query="+searchText) 
        //         .then((resp) => {
        //         this.store.serieTv = resp.data.results;
        //         })
        //         //debug
        //         console.log(this.store.film);
        //     }
        // },
    }


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

        <!-- <ul v-if="this.store.category === 'Film'" v-for="film in store.film">
            <li >{{film.title}}</li>
            <li >{{film.original_title}}</li>
            <li >{{film.original_language}}</li>
            <li >{{film.vote_average}}</li>
        </ul>
        <ul v-else v-for="serie in store.serieTv">
            <li >{{serie.name}}</li>
            <li >{{serie.original_name}}</li>
            <li >{{serie.original_language}}</li>
            <li >{{serie.vote_average}}</li>
        </ul> -->
    </div>
    <!-- <AppName/> -->
</template>

<style scoped>

</style>
