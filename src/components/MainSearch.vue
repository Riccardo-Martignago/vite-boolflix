<script>
export default {
    data() {
        return {
            testoRicerca: ''
        }
    }
}
</script>

<template>
    <div>
        <input type="text" v-model="testoRicerca" placeholder="Inserisci il nome del titolo da cercare">
        <button @click="$emit('filmSearch', testoRicerca)">CLICCA</button>
    </div>
</template>

<style lang="scss" scoped>
</style>