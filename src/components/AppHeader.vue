<script>
export default {
    name: 'AppHeader',
    emits: ['type-change'],
    data: () => ({
        selectedType: '',
        types: ["Bug", "Dark", "Dragon", "Electric", "Fairy", "Fighting", "Fire", "Flying", "Ghost", "Grass", "Ground", "Ice", "Normal", "Poison", "Psychic", "Rock", "Steel", "Water"]
    })
}
</script>

<template>
    <header>
        <select class="form-select" name="pokemon-types" v-model="selectedType"
            @change="$emit('type-change', selectedType)">
            <option value="">All</option>
            <option v-for="type in this.types">
                {{ type }}
            </option>
        </select>
    </header>
</template>

<style lang="scss" scoped>
header {
    display: flex;
    justify-content: center;
    padding-top: 20px;

    select {
        width: 10%;
    }
}
</style>