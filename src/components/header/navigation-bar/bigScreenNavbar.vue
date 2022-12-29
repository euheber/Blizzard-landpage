<template>
    <ul id="navigation">
        <li @click="handleGames">Jogos <i class="fa-solid fa-chevron-down btnGame"></i></li>
        <li @click="handleEsports">E-sports <i class="fa-solid fa-chevron-down btnEsport"></i></li>
        <li>Loja</li>
        <li>Notícia</li>
        <li>Suporte</li>
    </ul>

    <div id="profile-btns">
        <button id="create-account">Criar conta</button>
        <button id="login" @click="renderizar"><i class="fa-regular fa-user"></i> Logar</button>
    </div>

    <modalLoginVue ref="meuModalRef"/>
</template>

<script>

import modalLoginVue from '../Modal/modal-login.vue'
export default {
    components: { 
        modalLoginVue
    },
    name: 'Bigscreen',
    data: () => ({
        gameIcons: [
            'icons-banner-hero/game-1.png',
            'icons-banner-hero/game-2.png',
            'icons-banner-hero/game-3.png',
            'icons-banner-hero/game-4.png',
            'icons-banner-hero/game-5.png',
            'icons-banner-hero/game-6.png',
            'icons-banner-hero/game-7.png',
            'icons-banner-hero/game-8.png',
            'icons-banner-hero/game-9.png',
            'icons-banner-hero/game-10.png',
            'icons-banner-hero/game-11.png',
            'icons-banner-hero/game-12.png',
        ],
        tournamentIcons: [
            'icons-banner-hero/sport-1.png',
            'icons-banner-hero/sport-2.png',
            'icons-banner-hero/sport-3.png',
            'icons-banner-hero/sport-4.png'
        ]
    }),
    methods: {
        handleGames() {
            const games = document.querySelector('.btnGame')
            games.classList.toggle('active')
        },
        handleEsports() {
            const sports = document.querySelector('.btnEsport')
            sports.classList.toggle('active')
        },
        renderizar(){ 
            this.$refs.meuModalRef.handleM()
        }
    }
}
</script>



<style  src="../../../assets/scss/header/bigScreenNavbar.scss" scoped />

