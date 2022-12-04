<script>
import CountryFlag from "vue-country-flag-next";

export default {
  name: "AppCardSerie",
  components: {
    CountryFlag,
  },
  props: {
    info: Object,
  },
  methods: {
    getFlag(lang) {
      if (lang == "en") {
        return "gb";
      }
    },
  },
  computed: {
    vote() {
      return Math.ceil(this.info.vote_average / 2);
    },
  },
  data() {
    return {
      //
    };
  },
};
</script>

<template>
      <div class="card">
        <div class="poster">
          <img
            :src="`https://image.tmdb.org/t/p/w342${info.poster_path}`"
            :alt="info.name"
          />
        </div>
        <div class="title">
          {{ info.name }}
        </div>
        <div class="flag">
          <CountryFlag
            :country="getFlag(info.original_language)"
            size="normal"
          />
        </div>
        <div class="evaluation">
          <font-awesome-icon
            v-for="n in 5"
            :icon="n <= vote ? 'fa-star fa-solid' : 'fa-star fa-regular'"
          />
          {{ vote }}
        </div>
      </div>
</template>


<style lang="scss" scoped>
.card {    
    width: calc(100%/4 - 40px);
    padding: 20px;
    img{
        height: 500px;
    }
}
</style>
