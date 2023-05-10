<script>
import NavbarComp from './componets/NavbarComp.vue';
import axios from 'axios';
import { store } from './store';

export default {
    name: "app",
    components: {
        NavbarComp
    },
    data() {
        return {
            store
        }
    },
    methods: {
        AttivaRicerca() {
            // 
            axios.get(`https://api.themoviedb.org/3/search/movie?api_key=${store.Apikey}&query=${store.Ricerca}`)
                .then((elem) => {
                    console.log(elem.data.results)
                    const selezione = elem.data.results
                    store.ArrayFilm = selezione

                })
        }
    }
}
</script>

<template>
    <NavbarComp @apiCall="AttivaRicerca()" />
</template>

<style lang="scss">
@use './style/main.scss';
</style>
