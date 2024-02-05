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
    <div class="card text-center">
        <img :src="image" :alt="name" class="image-fluid rounded-circle">
        <h4>{{ number }}</h4>
        <h2>{{ name }}</h2>
        <h3>{{ type }}</h3>
    </div>
</template>

<style lang="scss" scoped></style>