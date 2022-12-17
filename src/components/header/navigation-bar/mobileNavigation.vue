<template>
    <div>
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

<style lang="scss" scoped>
* {
    text-align: center;
}

#listBox {
    width: 100%;
    display: flex;
    flex-direction: column;
    // min-height: 80vh;
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
    padding-top: 6rem;
    display: flex;
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

.esportsList{
    flex-wrap: wrap;
    display: flex;
    gap: 1rem;
    justify-content: center;

    li img {
        width: 40px;
        height: 40px;
    }
}

#mobileMenuFooter {
    width: 100%;
    background-color: black;
    text-align: center;
    display: flex;
    align-items: center;
    justify-content: space-evenly;
    padding: .5rem;
    margin-top: auto;
    align-self: flex-end;
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
    margin-block: 2rem;
    display: flex;
    justify-content: center;
    gap: 1rem;

    button {
        width: 25%;
        padding: .4rem;
        border-radius: 3.15px;

        &#create-account {
            border: 1px solid white;
        }

        &#login {
            background-color: #00AEFF;
        }
    }

}

.fadeAnimation-enter-active,
.fadeAnimation-leave-active,
.fadeAnimation-enter-active {
    transition: opacity .5s ease;
}

.fadeAnimation-enter-from,
.fadeAnimation-leave-to,
.fadeAnimation-enter-from,
.fadeAnimation-leave-to {
    opacity: 0;
}

.fadeAnimation-leave-active {
    transition: opacity .11s ease;
}
</style>