<script>
import MainSearch from './MainSearch.vue';
import axios from 'axios';
export default {
    data() {
        return {
            filmList: []
        }
    },
    components:{
        MainSearch
    },
    methods:{
        getMovie(movieName){
            axios.get('https://api.themoviedb.org/3/search/movie?api_key=6bb997fa15d25cbe7941a11291a8a501&query=' + 'ciao', {
                params: {
                    Name: movieName
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
        <MainSearch />
    </main>
</template>

<style scoped>
</style>