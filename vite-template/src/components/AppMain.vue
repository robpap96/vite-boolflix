<script>
import AppCard from './AppCard.vue';

export default {
    name: 'AppMain',
    components: {
        AppCard,
    },
    defineProps :{
        //msg: String
    },
    data(){
        return {
            //
        }
    },


}
</script>

<template>
    <AppCard/>
</template>

<style scoped>

</style>
