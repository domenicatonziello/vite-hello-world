<script>
export default {
    name: 'AppHero',
    data() {
        return {
            images: ['vue.svg', 'image-1.jpg'],
        }
    },
    methods: {
        buildImagePath(image) {
            const url = new URL(`../assets/${image}`, import.meta.url)
            return url.href;
        }
    }
}
</script>

<template>
    <img v-for="image in images" :src="buildImagePath(image)" :alt="image">
</template>

<style scoped>
img {
    max-width: 400px;
    display: block;
    margin: 10px 0;
}
</style>