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
        },
        Voto() {
            return Math.ceil(this.Info.vote_average / 2)
        }
    }
}
</script>

<template>
    <div id="comp">

        <div id="card">

            <div id="immagine-principale">
                <img :src="`https://image.tmdb.org/t/p/w342/${Info.poster_path}`" alt="" />
            </div>
            <div id="descrizione">
                <h4 class="card-title">{{ TitoloSerie() }}</h4>
                <hr>
                <div id="lang_vote">
                    <img :src="bandiere(Info.original_language)" alt="">
                    <h5 class="px-2">{{ Voto() }}</h5>
                    <div>
                        <i v-for="n in 5" class="fa-star" :class="(n <= Voto()) ? 'fa-solid' : 'fa-regular'"></i>
                    </div>
                </div>

                <p class="card-text ">{{ Info.overview }}</p>
            </div>

        </div>
    </div>
</template>

<style lang="scss" scoped>
#comp {

    display: flex;
    justify-content: space-between;

    #card {
        height: 250px;
        width: 200px;
        margin: 20px;
        position: relative;

        #immagine-principale {
            position: absolute;
            z-index: 2;

            img {
                height: 250px;
                width: 200px;
            }
        }

        #descrizione {
            position: absolute;
            overflow: hidden visible;
            max-height: 250px;
            display: none;

            #lang_vote {
                display: flex;

                img {
                    height: 30px;
                }
            }
        }

        &:hover {
            #immagine-principale {
                display: none;
            }

            #descrizione {
                display: block;
            }
        }


    }
}
</style>