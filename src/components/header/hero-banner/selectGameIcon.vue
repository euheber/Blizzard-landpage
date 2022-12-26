<template>
    <ul>
        <li v-for="infos in info" :key="infos.id">
            <button @click="handleSelectedGame(infos)"
                :class="[infos.highlight === this.highlightBtn ? infos.highlight : '']">
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
                icon: 'icons-banner-hero/game-1.png',
                title: 'Retorne à escuridão com o game Diablo IV',
                description: 'O retorno de Lilith traz uma era de escuridão e sofrimento',
                alt: 'Diablo IV',
                logo: '/icons-banner-hero/diabloLogo.svg',
                gif: '/icons-banner-hero/diabloIV.gif',
                cta: 'Jogue agora',
                highlight: 'diabloIV',
                divider: 20
            },
            {
                id: 2,
                game: 'Hearthstone',
                icon: 'icons-banner-hero/game-2.png',
                title: 'Novo pacote de expansão de Hearthstone',
                description: 'A Horda e a Aliança se encontraram no Vale Alterac para lutar',
                alt: 'Hearhstone',
                logo: '/icons-banner-hero/hsLogo.png',
                gif: '/icons-banner-hero/hearthstone.gif',
                cta: 'Reserve agora na pré-venda',
                highlight: 'HS',
                divider: 40,
            },
            {
                id: 3,
                game: 'World of Warcraft',
                icon: 'icons-banner-hero/game-3.png',
                title: 'Desbrave as Terras Sombrias em Shadowlands!',
                description: 'O que jaz além do mundo que você conhece?',
                alt: 'Warcraft',
                logo: '/icons-banner-hero/wowLogo.svg',
                gif: '/icons-banner-hero/world-of-warcraft.gif',
                cta: 'Reserve agora na pré-venda',
                highlight: 'wow',
                divider: 60,
            },
            {
                id: 4,
                game: 'Diablo HD',
                icon: 'icons-banner-hero/game-4.png',
                title: 'Matança de demônios em qualquer lugar',
                description: 'Descubra o que aconteceu entre Diablo II e Diablo III.',
                alt: 'Diablo HD',
                logo: '',
                gif: '',
                cta: 'Jogue agora',
                highlight: 'diabloHD',
                divider: 80,
            },
            {
                id: 5,
                game: 'Starcraft II',
                icon: 'icons-banner-hero/game-5.png',
                title: 'Jogo de estratégia em tempo real',
                description: 'Conquintes a galáxia como Terrano, Zerg ou Protoss.',
                alt: 'Starcraft II',
                logo: '',
                gif: '',
                cta: 'Jogue agora',
                highlight: 'starcraft',
                divider: 100,
            },
        ],
        highlightBtn: 'diabloIV'
    }),
    methods: {
        handleSelectedGame(infos) {
            this.highlightBtn = infos.highlight
            this.$emit('getData', infos)
        }
    },
}
</script>


<style src="../../../assets/scss/header/selectGameIcon.scss" lang="scss" scoped />

