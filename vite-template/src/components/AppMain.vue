<script>
import AppCardFilm from "./AppCardFilm.vue";
import AppCardSerie from "./AppCardSerie.vue";
import { store } from "../store";

export default {
  name: "AppMain",
  components: {
    AppCardFilm,
    AppCardSerie,
  },
  props: {
    //msg: String
  },
  data() {
    return {
      store,
    };
  },
};
</script>

<template>
  <div class="container">
      <div class="cards" v-if="this.store.category === 'Film'" >
        <AppCardFilm v-for="film in store.film" :info="film" />
      </div>
      <div class="cards" v-else="this.store.category === 'Serie'"  >
        <AppCardSerie v-for="serie in store.serieTv" :info="serie" />
      </div>
    </div>
</template>

<style lang="scss" scoped>

.container {
  max-width: 1500px;
  margin: 100px auto;
  .cards{
    display: flex;
    flex-wrap: wrap;
    padding: 20px 0;
  }
}     
</style>
