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
    .logo {
        width: 18%;
    }
    .logo img {
        width: 65%;
    }
  }
  .search-bar {
    width: 13%;
    padding: 30px 50px;
    right: 15px;
    position: absolute;
    display: inline-block;
        input {
            width: 100%;
            height: 34px;
            background-color: rgb(81, 76, 76);
            box-shadow: none;
            color: #fff;
            border: 1px solid transparent;
            outline: none;
            padding-left: 35px;
            font-size: 16px;
            transition: 0.3s ease all;
                &.toggle {
                width: 240px;
                border-color: #fff;
                }
        }
        select {
            width: 20%;
            margin-top: 2px;
            margin-right: 5px ;
            height: 24px;
            background-color: rgb(81, 76, 76);
            box-shadow: none;
            color: #fff;
            border: 1px solid transparent;
            outline: none;
            padding-left: 35px;
            font-size: 16px;
            transition: 0.3s ease all;
                &.toggle {
                width: 240px;
                border-color: #fff;
                }
        }
        .search-btn {
            width: 20%;
            margin-top: 2px;
            margin-right: 5px ;
            height: 24px;
            background-color: rgb(170, 21, 21);
            box-shadow: none;
            color: #fff;
            border: 1px solid transparent;
            outline: none;
  
     
        }
  }
}
</style>
