<script>
import { store } from '../store'
export default {
    name: "NavbarComp",
    data() {
        return {
            store
        }
    }
}
</script>

<template>
    <nav class="container">

        <span id="app-title" class="fw-bold fs-1 text-uppercase">boolflix</span>
        <div>
            <input type="text" placeholder="ricerca film o serie" v-model="store.Ricerca">
            <button @click.prevent="$emit('apiCall')" class="">Invio</button>
        </div>

    </nav>
</template>

<style lang="scss" scoped>
nav {
    display: flex;
    align-items: center;
    justify-content: space-between;

    #app-title {
        color: rgb(129, 23, 23);
    }
}
</style>