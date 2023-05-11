<script>
import { store } from '../store';
import FilmComp from './FilmComp.vue';

export default {
    name: "MainComp",
    data() {
        return {
            store
        }
    },
    components: {
        FilmComp
    }
}
</script>

<template>
    <div class="p-5">

        <div class="row" v-if="store.ArraySerie.length">
            <FilmComp v-for="(film, index) in store.ArrayFilm" :key="index" :Info="film" />
        </div>
        <div class="row" v-if="store.ArraySerie.length">
            <FilmComp v-for="(serie, index) in store.ArraySerie" :key="index" :Info="serie" />
        </div>

    </div>
</template>

<style lang="scss" scoped></style>