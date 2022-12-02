<script>
import CountryFlag from 'vue-country-flag-next'

export default {
    name: 'AppCardSerie',
    components: {
        CountryFlag,
    },
    props :{
        info: Object,
    },
    computed: {
        vote(){
            return Math.ceil(this.info.vote_average / 2)
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
            <li><img :src="`https://image.tmdb.org/t/p/w342${info.poster_path}`" alt=""></li>
            <li >{{info.name}}</li>
            <li><CountryFlag :country='info.original_language' size='normal'/></li>
            <li >
                <font-awesome-icon
                v-for="n in 5"
                :icon=" n <= vote ? 'fa-star fa-solid' : 'fa-star fa-regular'"
                />
                {{vote}}
            </li>
        </ul>

</template>

<style scoped>

</style>
