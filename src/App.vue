<script >
import axios from 'axios';
import { store } from './data/store';
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons?per=192'
import AppMain from './components/AppMain.vue'
export default {
    name: 'Pokévuex',
    components: { AppMain },
    created() {
        axios.get(endpoint).then(res => {
            store.characters = res.data.docs;
        })
    }
}
</script>

<template>
    <AppMain />
</template>

<style lang="scss">
@use './assets/scss/style.scss' as *;

body {
    background-color: #DB3C36;
}
</style>
