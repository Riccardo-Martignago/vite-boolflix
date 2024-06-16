<script>
export default {
    data() {
        return {
        }
    },  
    props:{
        filmList:{
        type: Array,
        required: true
        }
    }
}
</script>

<template>
    <section>
        <ul>
            <li v-for="films in filmList" :key="films.id">
                <h2>{{ films.title }}</h2>
                <p>{{ films.original_title }}</p>
                <p>{{ films.vote_average }}</p>
                <p>{{ films.original_language }}</p>
            </li>
        </ul>
    </section>
</template>

<style lang="scss" scoped>
</style>