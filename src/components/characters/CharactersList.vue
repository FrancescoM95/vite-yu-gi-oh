<script >
import { store } from '../../data/store'
import CharactersCard from './CharactersCard.vue';
export default {
    name: 'CharactersList',
    data: () => ({
        store
    }),
    components: { CharactersCard },
}
</script>

<template>
    <section id="characters-list">
        <div class="container">
            <div class="row row-cols-5 g-4">
                <div class="col" v-for="character in store.characters" :key="character.id">
                    <CharactersCard :name="character.name" :image="character.imageUrl" :number="character.number"
                        :type="character.type1" />
                </div>

            </div>
        </div>

    </section>
</template>

<style lang="scss" scoped>
#characters-list {
    height: calc(100vh - 130px);
    overflow-y: auto;
    border: 20px solid #CCD0CF;
    border-radius: 20px;
}

.row {
    background-color: #3d7993;
    padding: 15px 0;
}
</style>