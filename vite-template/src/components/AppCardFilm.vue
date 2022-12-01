<script>
 
export default {
    name: 'AppCardFilm',
    components: {

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
        <li >{{info.title}}</li>
        <li >{{info.original_language}}</li>
        <li >{{info.vote_average}}</li>
    </ul>

</template>

<style scoped>

</style>
