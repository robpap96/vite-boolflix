<script>
import AppHeader from './components/AppHeader.vue'
import AppMain from './components/AppMain.vue'
import {store} from "./store";

export default {
    name:'App',
    components: {
        AppHeader,
        AppMain,
    },
    methods: {

    },
    data() {
        return {
            store,
        }
    },

}
</script>

<template>
    <AppHeader/>
    <AppMain/>
</template>

<style lang="scss">
    @import './style/global.scss';
</style>
