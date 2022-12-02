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
    data(){
        return {
            //
        }
    },


}
</script>

<template>
        <ul>
            <li >{{info.name}}</li>
            <li><CountryFlag :country='info.original_language' size='normal'/></li>
            <li >{{info.vote_average}}</li>
        </ul>

</template>

<style scoped>

</style>
