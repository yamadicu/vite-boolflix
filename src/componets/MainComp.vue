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
    <div id="sfondo" class="p-5">

        <div class="col" v-if="store.ArraySerie.length">
            <FilmComp v-for="(film, index) in store.ArrayFilm" :key="index" :Info="film" />
        </div>
        <div class="col" v-if="store.ArraySerie.length">
            <FilmComp v-for="(serie, index) in store.ArraySerie" :key="index" :Info="serie" />
        </div>

    </div>
</template>

<style lang="scss" scoped>
#sfondo {
    background-color: grey;
    min-height: 90vh;
    display: flex;
    flex-direction: column;

    .col {
        display: flex;
        flex-direction: space-between;
        flex-wrap: wrap;
    }
}
</style>