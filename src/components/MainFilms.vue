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
                <span class="lang-icon lang-icon-en"></span>
                <span class="lang-icon lang-icon-aqc"></span>
                <span class="lang-icon lang-icon-cs"></span>
                <span class="lang-icon lang-icon-de"></span>
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