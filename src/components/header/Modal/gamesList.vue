<template>
  <div class="gamesBox">
    <ul id="gamesLi">
      <li v-for="({ icon, title, id }) in games" :key="id">
        <img :src="icon" alt="">
        <p>{{ title }}</p>
      </li>
    </ul>
      
  <div id="gamesListFooter">
      <img src="/icons-banner-hero/allGames.svg" alt="Ver todos os jogos"> Ver todos os jogos
      <img src="/icons-banner-hero/blizzardIcon.svg" alt="Aplicativo Battle.net"> Aplicativos Battle.net
      <img src="/icons-banner-hero/downloadIcon.svg" alt="Downloads"> Downloads
      <img src="/icons-banner-hero/comunityIcon.svg" alt="Fóruns dos jogos"> Fóruns dos jogos
    </div>
  </div>
</template>

<script>
export default {
  nmae: 'gameList',
  data: () => ({
    games: [
      { icon: 'icons-banner-hero/game-1.png', title: 'Diablo IV', id: 0 },
      { icon: 'icons-banner-hero/game-2.png', title: 'Hearthstone', id: 0 },
      { icon: 'icons-banner-hero/game-3.png', title: 'World of Warcraft', id: 0 },
      { icon: 'icons-banner-hero/game-4.png', title: 'Diablo Imortal', id: 0 },
      { icon: 'icons-banner-hero/game-5.png', title: 'Starcraft II', id: 0 },
      { icon: 'icons-banner-hero/game-6.png', title: 'Diablo II', id: 0 },
      { icon: 'icons-banner-hero/game-7.png', title: 'Diablo III', id: 0 },
      { icon: 'icons-banner-hero/game-8.png', title: 'Starcraft', id: 0 },
      { icon: 'icons-banner-hero/game-9.png', title: 'Arcades da Blizzard', id: 0 },
      { icon: 'icons-banner-hero/game-10.png', title: 'Overwatch 2', id: 0 },
      { icon: 'icons-banner-hero/game-11.png', title: 'Warcraft III', id: 0 },
      { icon: 'icons-banner-hero/game-12.png', title: 'Heroes of the storm', id: 0 },
    ]
  }),
}
</script>



<style src="../../../assets/scss/header/gamesList.scss" scoped/>

