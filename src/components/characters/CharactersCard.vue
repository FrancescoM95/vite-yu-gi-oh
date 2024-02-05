<script >

export default {
    name: 'CharactersCard',
    props: {
        name: String,
        image: String,
        type: String,
        number: String
    }
}
</script>

<template>
    <div class="card text-center p-3">
        <img :src="image" :alt="name" class="rounded-circle">
        <h5>{{ number }}</h5>
        <h2 class="fs-5">{{ name }}</h2>
        <h5 class="m-0">{{ type }}</h5>
    </div>
</template>

<style lang="scss" scoped>
.card {
    display: flex;
    flex-direction: column;
    align-items: center;
    height: 225px;
    background-color: #eeeeee;

    img {
        max-width: 100%;
        max-height: 50%;
        display: block;
        margin-bottom: 10px;
        flex-basis: 70%;
        flex-grow: 1;
    }

    * {
        cursor: pointer;
    }

    h5 {
        font-style: italic;
        font-weight: 400;
    }
}
</style>