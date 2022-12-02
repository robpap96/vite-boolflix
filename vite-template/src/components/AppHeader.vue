<script>
//import AppName  from './....AppName.vue'
import { store } from "../store";

export default {
  name: "AppHeader",
  components: {},
  defineProps: {
    //msg: String
  },
  data() {
    return {
      store,
    };
  },
  methods: {},
};
</script>

<template>
  <header>
    <div class="container">
      <div class="logo">
        <img src="../assets/Netflix-logo.png" alt="" />
      </div>
      <div class="search-bar">
        <form @submit.prevent="$emit('performSearch')">
          <input
            type="search"
            placeholder="Search Films or Series"
            v-model="store.searchText"
            required
          />
          <select
            v-model="store.category"
            name="films or series"
            id="category"
            form="carform"
            required
          >
            <option value="Film">Film</option>
            <option value="Serie">Serie</option>
          </select>
          <button type="submit" class="search-btn">Cerca</button>
        </form>
      </div>
    </div>
  </header>
</template>

<style lang="scss" scoped>
header {
  background-color: black;
  position: fixed;
  max-height: 100px;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;

  .container {
    max-width: 1500px;
    margin: auto;
    display: flex;
    justify-content: space-between;
  }
  .search-bar {
    padding: 30px 50px;
  }
  img {
    width: 14%;
  }
}
</style>
