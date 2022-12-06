<template>
    <ul>
        <li v-for="infos in info" :key="infos.id">
            <button @click="handleSelectedGame(infos)" :class="[infos.highlight === this.highlightBtn ? infos.highlight : '']">
                <img :src="infos.icon" :alt="infos.alt">
            </button>
        </li>
    </ul>
</template>

<script>
export default {
    name: 'Icons',
    data: () => ({
        info: [
            {
                id: 1,
                game: 'Diablo IV',
                icon: 'src/assets/icons-banner-herro/game-1.png',
                title: 'Retorne à escuridão com o game Diablo IV',
                description: 'O retorno de Lilith traz uma era de escuridão e sofrimento',
                alt: 'Diablo IV',
                bg: '../assets/bg-banners/bg-banner-diablo.jpg',
                logo: '',
                gif: '',
                cta: 'Jogue agora',
                highlight: 'diabloIV'
            },
            {
                id: 2,
                game: 'Hearthstone',
                icon: 'src/assets/icons-banner-herro/game-2.png',
                title: 'Novo pacote de expansão de Hearthstone',
                description: 'A Horda e a Aliança se encontraram no Vale Alterac para lutar',
                alt: 'Hearhstone',
                bg: '../assets/bg-banners/bg-banner-hearthstone.jpg',
                logo: '',
                gif: '',
                cta: 'Reserve agora na pré-venda',
                highlight: 'HS'
            },
            {
                id: 3,
                game: 'World of Warcraft',
                icon: 'src/assets/icons-banner-herro/game-3.png',
                title: 'Desbrave as Terras Sombrias em Shadowlands! ',
                description: 'O que jaz além do mundo que você conhece?',
                alt: 'Warcraft',
                bg: '../assets/bg-banners/bg-banner-warcraft.jpg',
                logo: '',
                gif: '',
                cta: 'Reserve agora na pré-venda',
                highlight: 'wow'
            },
            {
                id: 4,
                game: 'Diablo HD',
                icon: 'src/assets/icons-banner-herro/game-4.png',
                title: '',
                description: '',
                alt: '',
                bg: '',
                logo: '',
                gif: '',
                cta: '',
                highlight: 'diabloHD'
            },
            {
                id: 5,
                game: 'Starcraft II',
                icon: 'src/assets/icons-banner-herro/game-5.png',
                title: '',
                description: '',
                alt: '',
                bg: '',
                logo: '',
                gif: '',
                cta: '',
                highlight: 'starcraft'
            },
        ],
        highlightBtn: 'diabloIV'
    }),
    methods: {
        handleSelectedGame(infos){
            this.highlightBtn = infos.highlight 
            this.$emit('getData', infos)
        }
    },
}
</script>


<style lang="scss" scoped>
ul {
    display: flex;

    & li button {
        transition: .2s ease;
        filter: grayscale(100%);
        -webkit-filter: grayscale(100%);
        background-color: transparent;
    }
}

.diabloIV,
.HS,
.diabloHD,
.wow,
.starcraft {
    filter: grayscale(0);
    -webkit-filter: grayscale(0);
}
</style>