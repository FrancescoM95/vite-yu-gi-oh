<script >
import CharactersCard from './CharactersCard.vue';
export default {
    name: 'CharactersList',
    components: { CharactersCard, CharactersCard },
    props: {
        characters: Array
    }
}
</script>

<template>
    <section class="container">
        <div class="row row-cols-5">
            <div class="col" v-for="character in characters" :key="character.id">
                <CharactersCard :name="character.name" :image="character.imageUrl" :number="character.number"
                    :type="character.type1" />
            </div>

        </div>
    </section>
</template>

<style lang="scss" scoped></style>