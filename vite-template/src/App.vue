<script>
import AppHeader from './components/AppHeader.vue'
import AppMain from './components/AppMain.vue'
import {store} from "./store";
import axios from "axios";


export default {
    name:'App',
    components: {
        AppHeader,
        AppMain,
    },
    methods: {
        getData(category){
            if(category === 'Film'){
                axios.get("https://api.themoviedb.org/3/search/movie", {
                    params: {
                        api_key: "855b32a225edd597704e4c0ca5c50972",
                        query: this.store.searchText,
                        language: "it-IT",
                    }
                }) 
                .then((resp) => {
                this.store.film = resp.data.results;
                })

            } else {
                axios.get("https://api.themoviedb.org/3/search/tv", {
                    params: {
                        api_key: "855b32a225edd597704e4c0ca5c50972",
                        query: this.store.searchText,
                        language: "it-IT",
                    }
                }) 
                .then((resp) => {
                this.store.serieTv = resp.data.results;
                console.log(resp.data);
                })

            }
        },
    },
    data() {
        return {
            store,
        }
    },

}
</script>

<template>
    <AppHeader @performSearch="getData(this.store.category)"/>
    <AppMain/>
</template>

<style lang="scss">
    @import './style/global.scss';
</style>
