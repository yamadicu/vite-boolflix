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
    <div class="row p-5">
        <FilmComp v-for="(elem, index) in store.ArrayFilm" :key="index" :InfoFilm="elem" />
    </div>
</template>

<style lang="scss" scoped></style>