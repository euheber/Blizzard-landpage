<template>
    <div class="teste">
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
        <modalLoginVue ref="meuModalRef" />

        <div v-if="showGames">
            <gamesListVue />
        </div>

        <div v-if="showSports">
            <esportsListVue />
        </div>
    </div>
</template>

<script>

import modalLoginVue from '../Modal/modal-login.vue'
import esportsListVue from '../Modal/esportsList.vue'
import gamesListVue from '../Modal/gamesList.vue'
export default {
    components: {
        modalLoginVue,
        esportsListVue,
        gamesListVue
    },
    name: 'Bigscreen',
    data: () => ({
        showGames: false,
        showSports: false,
    }),
    methods: {
        handleGames() {
            const games = document.querySelector('.btnGame')
            games.classList.toggle('active')
            this.showGames = !this.showGames
            if (this.showSports) {
                this.showSports = !this.showSports
                const sports = document.querySelector('.btnEsport')
                sports.classList.toggle('active')
            }
        },
        handleEsports() {
            const sports = document.querySelector('.btnEsport')
            sports.classList.toggle('active')
            this.showSports = !this.showSports
        },
        renderizar() {
            this.$refs.meuModalRef.handleM()
        }
    }
}
</script>









<style  src="../../../assets/scss/header/bigScreenNavbar.scss" scoped />

