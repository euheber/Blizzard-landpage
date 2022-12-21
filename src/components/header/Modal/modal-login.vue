<template>
    <div id="modal" v-if="handleModal">

        <div class="X-icon" @click="this.handleModal = !this.handleModal">
            <i class="fa-solid fa-x"></i>
        </div>
        <div>
            <img src="/logo-battle-net.png" alt="Battlenet">

            <form @click.prevent="">

                <input type="text" placeholder="E-mail ou telefone"> <br>
                <input type="password" placeholder="Senha"><br>

                <button>Conectar-se</button>
            </form>

            <span class="text-style-white">ou conecte-se com</span>

            <ul>
                <li><i class="fa-brands fa-google"></i></li>
                <li><i class="fa-brands fa-apple fa-x4"></i></li>
                <li><i class="fa-brands fa-facebook"></i></li>
            </ul>

            <p class="text-style-white">
               <span class="text-style">Crie uma conta</span> Battle.net de graça
            </p>

            <p class="text-style">Não consegue logar?</p>
        </div>
    </div>
</template>

<script>
export default {
    name: "login",
    data: () => ({
        handleModal: true,
    }),
}
</script>



<style lang="scss" scoped src="../../../assets/scss/header/modal-login.scss" />

