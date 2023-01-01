<template>
    <div id="apiGamesContainer">
        <div id="headerContent">
            <div>
                <span>games</span>

                <h1>Jogos exclusivos</h1>

                <ul>
                    <li>icons</li>
                    <li>icons</li>
                    <li>icons</li>
                    <li>icons</li>
                </ul>
            </div>

            <a href="#"> <img src="icons-banner-hero/allGames.svg" alt="Icon1"> Ver todos os jogos</a>
        </div>

        <ul id="gamesList">
            <li v-for=" ({ category, image, logo }) in games" :key="category">
                <div class="logo-icon">
                    <img :src="image" class="background">
                    <img :src="logo" class="logo">
                </div>
            </li>

            <li class="all-games-box">
                <div class="all-games">
                    <img src="/logo-blizzard.png" alt="Blizzard"> <br>
                    <a href="#"> <img src="icons-banner-hero/allGames.svg" alt="Icon1"> Ver todos os jogos</a>
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
    async created() {
        const response = await fetch('https://api.brchallenges.com/api/blizzard/games')
        const games = await response.json()

        this.games = games
    },
}
</script>




<style src="../../assets/scss/mainContainer/gamesApi.scss" lang="scss" scoped/>
  