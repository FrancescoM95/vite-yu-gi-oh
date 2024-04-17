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
            <option value="">All types</option>
            <option v-for="type in this.types">
                {{ type }}
            </option>
        </select>
        <a href="https://fontmeme.com/it/font-pokemon/"><img src="https://fontmeme.com/permalink/240417/0694a084327fd54989dd82f04dcd6313.png" alt="font-pokemon" border="0" class="m-0"></a>
        <div class="circle-box">
            <div class="circle yellow"></div>
            <div class="circle green"></div>
            <div class="circle blue"></div>
        </div>
    </header>
</template>

<style lang="scss" scoped>
header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding-top: 20px;

    select {
        width: 10%;
    }

    .circle-box {
    display: flex;
    justify-content: space-between; 
    width: 100px; 
    }

    .circle {
        width: 30px; 
        height: 30px; 
        border-radius: 50%;
        border: 1px solid gray;
        box-shadow: 1px 1px 0px lightgray;
    }

    .yellow {
        background-color: yellow;
    }

    .green {
        background-color: green;
    }

    .blue {
        background-color: blue;
    }
}
</style>