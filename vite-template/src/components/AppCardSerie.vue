<script>
 
export default {
    name: 'AppCardSerie',
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
            <li >{{info.name}}</li>
            <li >{{info.original_language}}</li>
            <li >{{info.vote_average}}</li>
        </ul>

</template>

<style scoped>

</style>
