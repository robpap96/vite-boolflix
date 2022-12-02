<script>
import CountryFlag from 'vue-country-flag-next'

export default {
    name: 'AppCardFilm',
    components: {
        CountryFlag,
    },
    props :{
        info: Object,
    },
    methods: {
        getFlag(lang){
            if(lang == "en"){
                return "gb";
            }
        }
    },
    data(){
        return {
            //
        }
    },


}
</script>

<template>
    <ul>
        <li >{{info.title}}</li>
        <li><CountryFlag :country='getFlag(info.original_language) ' size='normal'/></li>
        <li >{{info.vote_average}}</li>
    </ul>

</template>

<style scoped>

</style>
