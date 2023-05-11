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
    <div id="back">

        <nav class="container">

            <span id="app-title" class="fw-bold fs-1 text-uppercase">boolflix</span>
            <div>
                <input type="text" placeholder="ricerca film o serie" v-model="store.Ricerca">
                <button @click.prevent="$emit('apiCall')" class="">Invio</button>
            </div>

        </nav>

    </div>
</template>

<style lang="scss" scoped>
#back {
    background-color: rgb(20, 20, 20);
    width: 100%;

    nav {

        min-height: 10vh;
        display: flex;
        align-items: center;
        justify-content: space-between;

        #app-title {
            color: rgb(129, 23, 23);
        }
    }
}
</style>