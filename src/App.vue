<script >
import axios from 'axios';
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons?per=30'
import AppMain from './components/AppMain.vue'
export default {
    name: 'Pokévuex',
    data: () => ({
        characters: []
    }),
    components: { AppMain },
    created() {
        axios.get(endpoint).then(res => {
            this.characters = res.data.docs;
            console.log(this.characters);
        })
    }
}
</script>

<template>
    <AppMain :characters="characters" />
</template>

<style lang="scss" scoped>
@use './assets/scss/style.scss' as *
</style>
