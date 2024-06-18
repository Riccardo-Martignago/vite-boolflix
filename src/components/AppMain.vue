<script>
import MainSearch from './MainSearch.vue';
import MainFilms from './MainFilms.vue';
import MainSeries from './MainSeries.vue';
import axios from 'axios';
export default {
    data() {
        return {
            filmList: [],
            seriesList: []
        }
    },
    components:{
        MainSearch,
        MainFilms,
        MainSeries
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
        getSeries(serieName){
            axios.get('https://api.themoviedb.org/3/search/tv?api_key=6bb997fa15d25cbe7941a11291a8a501&query=' + serieName, {
                params: {
                    name: serieName
                    }
                })
                .then((response) => {
                    this.seriesList = response.data.results
                    console.log(response.data.results);
                })
                .catch(function (error) {
                    console.log(error);
                })
                .finally(function () {
                    // always executed
            }); 
        },
        testoRicerca(testo) {
            this.getMovie(testo);
            this.getSeries(testo)
        }
    },
    created(){
        this.getMovie();
        this.getSeries();
    }
}
</script>

<template>
    <main>
        <h1>MAIN</h1>
        <MainSearch @Searched="testoRicerca"/>
        <MainFilms :filmList="filmList"/>
        <MainSeries :seriesList="seriesList"/>
    </main>
</template>

<style scoped>

</style>