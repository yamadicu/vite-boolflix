<script>
export default {
    name: 'FilmComp',
    props: ['InfoFilm'],

}
</script>

<template>
    <div class="col-2 mb-5">
        <div class="card card-film">
            <img src="#" class="card-img-top" :alt="InfoFilm.original_title">
            <div class="card-body">
                <h4 class="card-title">{{ InfoFilm.original_title }}</h4>
                <hr>
                <div>
                    <h5>{{ InfoFilm.original_language }}</h5>
                    <h5>{{ InfoFilm.vote_average.toFixed(2) }}</h5>
                </div>

                <p class="card-text ">{{ InfoFilm.overview }}</p>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.card-film {
    max-height: 250px;
    overflow: hidden visible;
}
</style>