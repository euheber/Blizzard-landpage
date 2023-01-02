<template>
    <div id="footer-content">
       <div class="footer-text-content">
            <img src="/logo-blizzard.png" alt="Bllizard">    
            <h1>Baixe agora o battle.net</h1>   

            <ul>
                <li> 
                    <img src="/icons/allInOne.svg" alt="Icone: Todos os jogos">
                    Seus jogos em um só lugar
                </li>
                <li>
                    <img src="/icons/playWithFriends.svg" alt="Icone: Jogar com os amigos">
                    Conecte-se aos seus amigos
                </li>
                <li>
                    <img src="/icons/buy.svg" alt="icone: compre os jogos">
                    Compre jogos e itens digitais
                </li>
            </ul>

            <button v-html="system"></button> <br>

            <a><img src="/icons/cellphone.svg" alt="Icone: celular"> Também disponível como aplicativo móvel</a>
       </div>
       <div class="app-img-box">
            <img src="/ilustrations/app-mini.png" alt="">
       </div>
    </div>
</template>

<script>
export default {
    name: 'footer',
    data: () => ({
        nome: 'heber'
    }),
    computed: { 
        system(){ 
            if(navigator.platform == 'Win32' || navigator.platform == 'Win16'){ 
                return `<i class="fa-brands fa-windows">` + `</i>` + ' Baixar para Windows'
            } else { 
                return `<i class="fa-brands fa-apple"></i>Baixar para MacOS`
            }
        }
    }
}
</script>



<style lang="scss" scoped src="../../assets/scss/footer/footerComponent.scss" />