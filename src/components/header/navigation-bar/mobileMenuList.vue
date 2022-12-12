<template>
    <div id="mobileMenu">
            <button @click="handleGameList">Jogos<i class="fa-solid fa-chevron-down btnGame"></i></button>   
            <ul v-if="toggleGamesList">
                    <li>teste</li>
            </ul>
    
            <button @click="handleEsportList">Esportes<i class="fa-solid fa-chevron-down btnEsport"></i></button> 
            <ul v-if="toggleEsportList">
                    <li>
                        teste
                    </li>
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

</template>

<script>

export default {
    name: 'mobileMenuList',
    data: () => ({
        toggleGamesList: false,
        toggleEsportList: false,
    }),
    methods: { 
        handleGameList(){
            this.toggleGamesList = !this.toggleGamesList
            const btnGame = document.querySelector('.btnGame')
            btnGame.classList.toggle('active')
            console.log(btnGame)
        },
        handleEsportList(){
            this.toggleEsportList = !this.toggleEsportList
            const btnEsport = document.querySelector('.btnEsport')
            btnEsport.classList.toggle('active')
        }
    }
}
</script>

<style lang="scss" scoped>
#mobileMenu {
    z-index: 99;
    background: linear-gradient(180deg, #020203 0%, rgba(14, 17, 23, 0.92) 96.35%, rgba(14, 17, 23, 0.9) 100%);
    backdrop-filter: blur(6px);
    position: absolute;
    top: 1px;
    bottom: 1rem;
    right: 0;
    width: 100%;
    text-align: center;
    display: flex;
    flex-direction: column;
    padding-top: 6rem;
}

button{
    background-color: transparent;
    color: white;
    padding: 12px;
    display: flex;
    gap: 14px;
    justify-content: center;
    align-items: center;
    width: 25%;
    margin: 0 auto;
}

ul li{
    color: white;
}


.btnGame{ 
    transition: .2s ease;
    &.active{
        transform: rotate(3.142rad)
    }

}

.btnEsport{
    transition: .2s ease;
    &.active{
        transform: rotate(3.142rad)
    }

}
</style>