<template>
    <div id="apiGamesContainer">
        <div id="headerContent">
            <span>games</span>

            <h1>Jogos exclusivos</h1>

            <ul>
                <li>icons</li>
                <li>icons</li>
                <li>icons</li>
                <li>icons</li>
            </ul>

            <a href="#"> <img src="icons-banner-hero/allGames.svg" alt="Icon1"> Ver todos os jogos</a>
        </div>

        <ul id="gamesList">
            <li v-for=" ({category, image, logo}) in games" :key="category">
                <div class="logo-icon">
                    <img :src="image" class="background">
                    <img :src="logo" class="logo">
                </div>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'GameApi',
    data: () => ({
        games: ''
    }),
    methods: {
    },
    async created() {
        const response = await fetch('https://api.brchallenges.com/api/blizzard/games')
        const games = await response.json()

       this.games = games
    },
}
</script>



<style src="../../assets/scss/mainContainer/gamesApi.scss" lang="scss" scoped/>
  