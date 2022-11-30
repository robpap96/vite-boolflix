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

    },
    data() {
        return {
            store,
        }
    },
    created(){
        axios.get("https://api.themoviedb.org/3/search/movie?api_key=855b32a225edd597704e4c0ca5c50972&language=en-US&page=1&include_adult=false") 
        .then((resp) => {
            // this.store.film = resp
            console.log(resp);
        })
    }
}
</script>

<template>
    <AppHeader/>
    <AppMain/>
</template>

<style lang="scss">
    @import './style/global.scss';
</style>
