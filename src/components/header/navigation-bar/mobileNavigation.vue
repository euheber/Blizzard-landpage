<template>
    <div>
        <button id="openMobileMenu" @click="this.handleMobileMenu = !this.handleMobileMenu">
            <i class="fa-solid fa-bars mobile-btn"></i>
        </button>
 
        <Transition name="grow">
            <div id="mobileMenu" v-if="handleMobileMenu">
                <div id="listBox">
                    <button @click="handleGameList">Jogos<i class="fa-solid fa-chevron-down btnGame"></i></button>
                    <Transition name="games">
                        <ul v-if="toggleGamesList" class="gamesList">
                            <li v-for="game in gameIcons" :key="game.indexOf">
                                <img :src="game">
                            </li>
                        </ul>
                    </Transition>

                    <button @click="handleEsportList">Esportes<i
                            class="fa-solid fa-chevron-down btnEsport"></i></button>

                    <ul v-if="toggleEsportList">
                        <li>Esportes</li>
                    </ul>


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
                </div>

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
        </Transition>

    </div>
</template>

<script>

export default {
    name: 'mobileMenuList',
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

<style lang="scss" scoped>
* {
    text-align: center;
}

#listBox {
    margin-top: 2rem;
    margin: 0 auto;
}

#openMobileMenu {
    background-color: transparent;
    font-size: 2rem;
    color: rgba(255, 255, 255, 0.651);
    position: relative;
    z-index: 99;
}

#mobileMenu {
    position: absolute;
    right: 0;
    top: 0;
    width: 100%;
    z-index: 98;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    background: linear-gradient(180deg, #020203 0%, rgba(14, 17, 23, 0.92) 96.35%, rgba(14, 17, 23, 0.9) 100%);
    backdrop-filter: blur(6px);

    button {
        background-color: transparent;
        color: white;
        display: flex;
        gap: 14px;
        align-items: center;
        width: 100%;
        justify-content: center;
    }

    ul li {
        color: white;
    }

}

.gamesList {
    flex-wrap: wrap;
    display: flex;
    gap: 1rem;
    justify-content: center;

    li img {
        width: 30px;
        height: 30px;
    }
}

#mobileMenuFooter {
    align-self: end;
    position: absolute;
    bottom: 0;
    width: 100%;
    background-color: black;
    text-align: center;
    display: flex;
    align-items: center;
    justify-content: space-evenly;
    padding: .5rem;
}

.btnGame {
    transition: .2s ease;

    &.active {
        transform: rotate(3.142rad);
        color: #00AEFF;
        animation-delay: .5s;
    }

}

.btnEsport {
    &.active {
        transform: rotate(3.142rad);
        color: #00AEFF;
    }
}


#profile-btns {
    margin-top: 2rem;
    display: flex;
    justify-content: center;
    gap: 1rem;
    button{
        width: 25%;
        padding: .4rem;
        border-radius: 3.15px;
        &#create-account{
            border: 1px solid white;
        }

        &#login{
            background-color: #00AEFF;
        }
    }
   
}

.grow-enter-active,
.grow-leave-active,
.games-enter-active
{
    transition: opacity .5s ease;
}

.grow-enter-from,
.grow-leave-to,
.games-enter-from,
.games-leave-to {
    opacity: 0;
}

.games-leave-active{
    transition: opacity .11s ease;
}
</style>