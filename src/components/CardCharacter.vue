<script>
    export default {
        props:['posts'],
        setup () {
            

            return {}
        }
    }
</script>

<template>
    <div class="text-center">
        <img class="img-fluid rounded-circle" :src="posts.image" :alt="posts.name">
        <h3 class="status mt-4">{{ posts.name }}</h3>
        <h4 class="species ">{{ posts.species }}</h4>
        <h5 class="status">{{ posts.status }}</h5>
    </div>
</template>

<style lang="scss" scoped>

</style>