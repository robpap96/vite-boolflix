<script>
import AppCardFilm from './AppCardFilm.vue';
import AppCardSerie from './AppCardSerie.vue';
import { store } from '../store';

export default {
    name: 'AppMain',
    components: {
        AppCardFilm,
        AppCardSerie,
    },
    props :{
        //msg: String
    },
    data(){
        return {
            store,
        }
    },


}
</script>

<template>
    <div v-if="this.store.category === 'Film'">
        <AppCardFilm v-for="film in store.film" :info="film" />
    </div>
    <div v-else="this.store.category === 'Serie'">
        <AppCardSerie v-for="serie in store.serieTv" :info="serie" />
    </div>
</template>

<style scoped>

</style>
