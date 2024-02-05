<script>
export default {
    name: 'Pokemon card',
    props:
    {
        id: String,
        name: String,
        type: String,
        image: String
    }
}
</script>
<template>
    <div class="text-center">
        <img :src="image" :alt="name">
        <h3>{{ name }}</h3>
        <h4>{{ type }}</h4>
    </div>
</template>
<style lang="scss" scoped>
div {
    img {
        width: 150px;
    }

    h3 {
        font-style: italic;
        font-weight: bold;
        font-size: 1.5rem;
    }
}
</style>