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
        <h2>FILM</h2>
        <ul>
            <li v-for="films in filmList" :key="films.id">
                <img :src="'https://image.tmdb.org/t/p/w500' + films.backdrop_path" alt="">
                <h2>{{ films.title }}</h2>
                <p>{{ films.original_title }}</p>
                <p>{{ starRating(films.vote_average) }}</p>
                <p>{{ films.original_language }}</p>
                <span :class="'lang-icon lang-icon-' + (films.original_language)"></span>
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