<template>
    <ul class="menu-list">
        <li>Componente</li>
        <li>Componente</li>
        <li>Loja</li>
        <li>Notícias</li>
        <li>Suporte</li>
    </ul>

    <div id="btns">
        <button>Criar conta</button>
        <button>Criar Logar</button>
    </div>

    <i class="fa-solid fa-bars mobile-btn"></i>
</template>

<script>
export default {
    name: 'navigation',
}
</script>

<style lang="scss" scoped>
.mobile-btn {
    font-size: 2rem;
    color: rgba(255, 255, 255, 0.7);
}

@media screen and (max-width: 375px) {

    #btns,
    .menu-list {
        display: none;
    }
}
</style>