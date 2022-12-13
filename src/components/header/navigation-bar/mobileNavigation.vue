<template>
    <div>
        <button id="openMobileMenu" @click="this.handleMobileMenu = !this.handleMobileMenu">
            <i class="fa-solid fa-bars mobile-btn"></i>
        </button>

        <div id="mobileMenu" v-if="handleMobileMenu">
            <button @click="handleGameList">Jogos<i class="fa-solid fa-chevron-down btnGame"></i></button>
            <ul v-if="toggleGamesList">
                <li>Jogos</li>
            </ul>

            <button @click="handleEsportList">Esportes<i class="fa-solid fa-chevron-down btnEsport"></i></button>
           <transition>
            <ul v-if="toggleEsportList">
                <li>
                    Esportes
                </li>
            </ul>
           </transition>

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

            <div id="mobileMenuFooter">
                <p style="color: white">teste</p>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    name: 'mobileMenuList',
    data: () => ({
        toggleGamesList: false,
        toggleEsportList: false,
        handleMobileMenu: false
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

*{
    text-align: left;
}
#mobileMenu {
    z-index: 99;
    background: linear-gradient(180deg, #020203 0%, rgba(14, 17, 23, 0.92) 96.35%, rgba(14, 17, 23, 0.9) 100%);
    backdrop-filter: blur(6px);
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
    min-height: 60vh;
    display: flex;
    flex-direction: column;
    justify-content: center;

    button {
        background-color: transparent;
        color: white;
        display: flex;
        gap: 14px;
        align-items: center;
        width: 25%;
    }

    ul li {
        color: white;
    }

}

#mobileMenuFooter {
    align-self: end;
    position: absolute;
    bottom: 0;
    border: 1px solid #00AEFF;;
    width: 100%;
}

.btnGame {
    transition: .3s ease;

    &.active {
        transform: rotate(3.142rad);
        color: #00AEFF;;
    }

}

.btnEsport {
    transition: .3s ease;

    &.active {
        transform: rotate(3.142rad);
        color: #00AEFF;;
    }

}
</style>