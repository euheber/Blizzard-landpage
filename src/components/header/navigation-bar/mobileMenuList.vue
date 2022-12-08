<template>
    <div>
        <button @click="teste">Jogos<i class="fa-solid fa-chevron-down"></i></button>

        <ul v-if="handleToggleMenu">
            <li>
                <p>Diablo® II ressurected</p>
            </li>
            <li>
                <p>Overwatch® 2</p>
            </li>
            <li>
                <p>World of Warcraft®</p>
            </li>
            <li>
                <p>Hearthstone®</p>
            </li>
            <li>
                <p>Heroes of the storm®</p>
            </li>
            <li>
                <p>Warcraft® III Reforged</p>
            </li>
            <li>
                <p>Diablo® IV</p>
            </li>
            <li>
                <p>Diablo® Immortal</p>
            </li>
            <li>
                <p>Diablo® III</p>
            </li>
            <li>
                <p>StarCraft® II</p>
            </li>
            <li>
                <p>StarCraft® Remastered</p>
            </li>
            <li>
                <p>Arcade da Blizzard®</p>
            </li>
        </ul>
    </div>

</template>

<script>

export default {
    name: 'mobileMenuList',
    data: () => ({
        handleToggleMenu: false
    }),
    methods: {
        teste() {
            this.handleToggleMenu = !this.handleToggleMenu
        }
    }
}
</script>

<style lang="scss" scoped>
div {
    z-index: 99;
    background-color: transparent;
    // position: absolute;
    top: 1px;
    bottom: 1rem;
    right: 0;
    width: 100%;
    text-align: right;
    border: 1px solid red;
}
</style>