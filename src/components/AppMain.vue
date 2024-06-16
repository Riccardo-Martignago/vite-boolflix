<script>
import MainSearch from './MainSearch.vue';
import MainFilms from './MainFilms.vue';
import axios from 'axios';
import { CalculationInterpolation } from 'sass';
export default {
    data() {
        return {
            filmList: []
        }
    },
    components:{
        MainSearch,
        MainFilms
    },
    methods:{
        getMovie(movieName){
            axios.get('https://api.themoviedb.org/3/search/movie?api_key=6bb997fa15d25cbe7941a11291a8a501&query=' + movieName, {
                params: {
                    name: movieName
                    }
                })
                .then((response) => {
                    this.filmList = response.data.results
                    console.log(response.data.results);
                })
                .catch(function (error) {
                    console.log(error);
                })
                .finally(function () {
                    // always executed
            }); 
        },
        testoFilm(testo) {
            this.getMovie(testo)
        }
    },
    created(){
        this.getMovie();
    }
}
</script>

<template>
    <main>
        <h1>MAIN</h1>
        <MainSearch @filmSearch="testoFilm"/>
        <MainFilms :filmList="filmList"/>
    </main>
</template>

<style scoped>
</style>