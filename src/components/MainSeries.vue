<script>
export default {
    data() {
        return {
        }
    },  
    props:{
        seriesList:{
        type: Array,
        required: true
        }
    },
    methods:{
        starRating(numb){
            return Math.ceil((numb / 10)* 5);
        }
    }
}
</script>

<template>
    <section>
        <h2>SERIE TV</h2>
        <ul>
            <li v-for="serie in seriesList" :key="serie.id">
                <img :src="'https://image.tmdb.org/t/p/w500' + serie.backdrop_path" :alt="serie.name">
                <h2>{{ serie.name }}</h2>
                <p>{{ serie.original_name }}</p>
                <p>{{ starRating(serie.vote_average) }}</p>
                <p>{{ serie.original_language }}</p>
                <span :class="'lang-icon lang-icon-' + (serie.original_language)"></span>
            </li>
        </ul>
    </section>
</template>

<style lang="scss" scoped>
    @use '../assets/lang-flags.scss' as*;
    .lang-icon {
        background-image: url(../assets/lang-flags.png);
    }
    .lang-icon {
    width: 25px;
    height: 15px;
    display: inline-block;
    background-image: url('../assets/lang-flags.png');
    background-size: auto;
}
</style>