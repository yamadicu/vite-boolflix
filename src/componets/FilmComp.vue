<script>
export default {
    name: 'FilmComp',
    props: ['Info'],
    methods: {
        bandiere(x) {
            x = x.toUpperCase();
            if (x == 'EN') {
                x = 'GB'
                return `https://flagsapi.com/${x}/shiny/64.png`
            } else if (x == 'JA') {
                x = 'JP'
                return `https://flagsapi.com/${x}/shiny/64.png`
            } else if (x == 'FA') {
                x = 'BG'
                return `https://flagsapi.com/${x}/shiny/64.png`
            } else if (x == 'ZH') {
                x = 'JP'
                return `https://flagsapi.com/${x}/shiny/64.png`
            } else if (x == 'KO') {
                x = 'HK'
                return `https://flagsapi.com/${x}/shiny/64.png`
            } else if (x == 'TA') {
                x = 'TH'
                return `https://flagsapi.com/${x}/shiny/64.png`
            } else if (x == 'XX') {
                x = 'ZM'
                return `https://flagsapi.com/${x}/shiny/64.png`
            }
            return `https://flagsapi.com/${x}/shiny/64.png`
        },
        TitoloSerie() {
            if (this.Info.original_title) {
                return this.Info.original_title
            } else {
                return this.Info.original_name
            }
        }
    }
}
</script>

<template>
    <div class="col-2 mb-5">
        <div class="card card-film">
            <img :src="`https://image.tmdb.org/t/p/w342/${Info.poster_path}`" class="card-img-top" alt="">
            <div class="card-body">
                <h4 class="card-title">{{ TitoloSerie() }}</h4>
                <hr>
                <div id="lang_vote">
                    <img :src="bandiere(Info.original_language)" alt="">
                    <h5 class="px-2">{{ Info.vote_average.toFixed(1) }}</h5>
                </div>

                <p class="card-text ">{{ Info.overview }}</p>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.card-film {
    max-height: 250px;
    width: 200px;
    overflow: hidden visible;

    img {
        height: 250px;
    }

    #lang_vote {
        display: flex;

        img {
            height: 30px;
        }
    }
}
</style>