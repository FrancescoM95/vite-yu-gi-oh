<script >
import CharactersList from './characters/CharactersList.vue';
export default {
    name: 'AppMain',
    props: {
        characters: Array
    },
    components: { CharactersList }
}
</script>

<template>
    <main>
        <CharactersList :characters="characters" />
    </main>
</template>

<style lang="scss" scoped></style>
