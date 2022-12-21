<template>
    <div>
            <modalLoginVue />

        <button id="openMobileMenu" @click="this.handleMobileMenu = !this.handleMobileMenu">
            <i class="fa-solid fa-bars mobile-btn"></i>
        </button>

        <Transition name="fadeAnimation">
            <div id="mobileMenu" v-if="handleMobileMenu">
                <div id="listBox">
                    <button @click="handleGameList">Jogos<i class="fa-solid fa-chevron-down btnGame"></i></button>
                    <Transition name="fadeAnimation">
                        <ul v-if="toggleGamesList" class="gamesList">
                            <li v-for="game in gameIcons" :key="game.indexOf">
                                <img :src="game">
                            </li>
                        </ul>
                    </Transition>

                    <button @click="handleEsportList">E-sports<i
                            class="fa-solid fa-chevron-down btnEsport"></i></button>

                   <Transition name="fadeAnimation">
                    <ul v-if="toggleEsportList" class="esportsList">
                        <li v-for="sports in tournamentIcons" :key="sports.indexOf">
                                <img :src="sports">
                        </li>
                    </ul>
                   </Transition>

                    <ul>
                        <li>
                            <p>Loja</p>
                        </li>
                        <li>
                            <p>Notícias</p>

                        </li>
                        <li>
                            <p>Suporte</p>
                        </li>
                    </ul>

                    <div id="profile-btns">
                        <button id="create-account">Criar conta</button>
                        <button id="login"><i class="fa-regular fa-user"></i> Logar</button>
                    </div>

                    <div id="mobileMenuFooter">
                        <img src="/icons-banner-hero/blizzardIcon.svg" alt="">
                        <img src="/icons-banner-hero/allGames.svg" alt="">
                        <img src="/icons-banner-hero/comunityIcon.svg" alt="">
                        <img src="/icons-banner-hero/downloadIcon.svg" alt="">
                        <img src="/icons-banner-hero/tournamentIcon.svg" alt="">
                    </div>
                </div>
            </div>
        </Transition>

    </div>
</template>

<script>
import modalLoginVue from '../Modal/modal-login.vue'
export default {
    name: 'navbar',
    components: {
        modalLoginVue,
    },
    data: () => ({
        toggleGamesList: false,
        toggleEsportList: false,
        handleMobileMenu: false,
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
        tournamentIcons:[
            'icons-banner-hero/sport-1.png',
            'icons-banner-hero/sport-2.png',
            'icons-banner-hero/sport-3.png',
            'icons-banner-hero/sport-4.png'
        ]
    }),
    methods: {
        handleGameList() {
            if (this.toggleEsportList) {
                const btnEsport = document.querySelector('.btnEsport')
                btnEsport.classList.toggle('active')
                this.toggleEsportList = !this.toggleEsportList
            }
            this.toggleGamesList = !this.toggleGamesList
            const btnGame = document.querySelector('.btnGame')
            btnGame.classList.toggle('active')

        },
        handleEsportList() {
            if (this.toggleGamesList) {
                const btnGame = document.querySelector('.btnGame')
                btnGame.classList.toggle('active')
                this.toggleGamesList = !this.toggleGamesList
            }
            this.toggleEsportList = !this.toggleEsportList
            const btnEsport = document.querySelector('.btnEsport')
            btnEsport.classList.toggle('active')
        }
    }
}
</script>

<style src="../../../assets/scss/header/mobileNavigation.scss" lang="scss" scoped />

