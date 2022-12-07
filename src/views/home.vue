<template>
  <header>
    <img src="src/assets/bg-banners/bg-banner-diablo.jpg"  :class="[gameBgPosition == 'diabloIV' ? gameBgPosition : 'default']">
    <img src="src/assets/bg-banners/bg-banner-hearthstone.jpg"  :class="[gameBgPosition == 'HS' ? gameBgPosition : 'default']">
    <img src="src/assets/bg-banners/bg-banner-warcraft.jpg"  :class="[gameBgPosition == 'wow' ? gameBgPosition : 'default']">
    <nav>
      <a href="" target="_blank">
        <img src="../assets/logo-blizzard.png" alt="Blizzard">
      </a>
      <navigation />
    </nav>
    <div class="divider"></div>
   
    <gameSelectionVue @getBg="handleBgStyle"/>
  
   
  </header>
  <div class="second-divider"></div>
</template>

<script>

import navigation from '../components/header/navigation-bar/navigation.vue'
import gameSelectionVue from '../components/header/hero-banner/gameSelection.vue';
export default {
  name: 'Home',
  components: {
    navigation,
    gameSelectionVue
  },
  data: () => ({
    gameBgPosition: 'diabloIV'
  }),
  methods: {
    handleBgStyle(style) {
      this.gameBgPosition = style.highlight
    }
  }
}
</script>
<style lang="scss" scoped>
header {
  min-height: 550px;
  width: 100%;
  background-size: cover;
  background-repeat: no-repeat;
  position: relative;
  overflow: hidden;
}

.diabloIV{
  position: absolute;
  min-height: 550px;
  right: -650px;
  z-index: -1;
}

.HS{
  position: absolute;
  min-height: 550px;
  right: -300px;
  z-index: -1;
}

.wow{
  position: absolute;
  min-height: 550px;
  right: -250px;
  z-index: -1;
}

.default{
  position: absolute;
  opacity: 0;
  min-height: 550px;
  right: -250px;
}

nav {
  padding: 1.5rem;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.divider {
  border: 1.5px solid rgba(255, 255, 255, 0.1);
  width: 100%;
  height: 5px;
  position: relative;

  &::after {
    position: absolute;
    content: '';
    width: 43px;
    height: 3px;
    background-color: #00AEFF;
    left: 1.5rem;
    bottom: 0px;
  }
}

.second-divider {
  border: 1.5px solid rgba(255, 255, 255, 0.1);
  width: 100%;
  height: 5px;
  position: relative;
  background-color: black;

  &::after {
    position: absolute;
    content: '';
    width: 202px;
    height: 3px;
    background-color: #00AEFF;
    left: -1rem;
    bottom: 0px;
  }
}
</style>