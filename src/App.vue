<script >
import axios from 'axios';
import { store } from './data/store';
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons?per=1000'
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue'

export default {
    name: 'Pokévuex',
    components: { AppMain, AppHeader },
    created() {
        axios.get(endpoint).then(res => {
            store.characters = res.data.docs;
        })
    },
    methods: {
        changeType(type) {
            if (type) {
                const searchEndpoint = `${endpoint}eq[type1]=${type}`
                axios.get(searchEndpoint).then(res => {
                    store.characters = res.data.docs;
                })
            } else {
                axios.get(endpoint).then(res => {
                    store.characters = res.data.docs;
                })
            }
        }
    }
}
</script>

<template>
    <div class="container">
        <AppHeader @type-change="changeType" />
        <AppMain />
    </div>
</template>

<style lang="scss">
@use './assets/scss/style.scss' as *;

body {
    background-color: #DB3C36;
}
</style>
