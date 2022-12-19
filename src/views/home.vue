<template>
  <header>
    <img src="/bg-banners/bg-banner-diablo.jpg"
      :class="[gameBgPosition == 'diabloIV' ? gameBgPosition : 'default']">
    <img src="/bg-banners/bg-banner-hearthstone.jpg"
      :class="[gameBgPosition == 'HS' ? gameBgPosition : 'default']">
    <img src="/bg-banners/bg-banner-warcraft.jpg"
      :class="[gameBgPosition == 'wow' ? gameBgPosition : 'default']">
      <img src="/bg-banners/bg-banner-starcraft.jpg"
      :class="[gameBgPosition == 'starcraft' ? gameBgPosition : 'default']">
      <img src="/bg-banners/bg-banner-diablo-immortal.jpg"
      :class="[gameBgPosition == 'diabloHD' ? gameBgPosition : 'default']">

     
    <nav>
      <a href="" target="_blank">
        <img src="/logo-blizzard.png" alt="Blizzard" id="logo">
      </a>
      <mobileMenuList/>
    </nav>
    <div class="divider">
    </div>

    <gameSelectionVue @getBg="handleBgStyle" />

  </header>
  <div class="second-divider" :style='`width:${divider}%`'></div>
</template>

<script>

import navigation from '../components/header/navigation-bar/navigation.vue'
import gameSelectionVue from '../components/header/hero-banner/gameSelection.vue';
import mobileMenuList from '../components/header/navigation-bar/mobileNavigation.vue'
export default {
  name: 'Home',
  components: {
    navigation,
    gameSelectionVue,
    mobileMenuList
  },
  data: () => ({
    gameBgPosition: 'diabloIV',
    divider: ''
  }),
  methods: {
    handleBgStyle(style) {
      this.gameBgPosition = style.highlight
      this.divider = style.divider
    }
  }
}
</script>
<style lang="scss" scoped>


header {
  height: 550px;
  width: 100%;
  background-size: cover;
  background-repeat: no-repeat;
  position: relative;
  overflow: hidden;
}

nav {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin: 0 auto;
  padding: 1rem;
}

nav a {
  z-index: 99;
}

#logo {
  height: 32px;
  width: 69.41908264160156px;
}

.divider {
  border: 1.5px solid rgba(255, 255, 255, 0.1);
  width: 100%;
  height: 5px;
  position: relative;
  z-index: 99;
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
  height: 5px;
  position: relative;
  background-color: #00AEFF;
  width: 20%;
  transition: .5s ease;
  border-radius: 0px 4px 4px 0px;
}

.diabloIV {
  position: absolute;
  min-height: 550px;
  right: -650px;
  z-index: -1;
}

.HS {
  position: absolute;
  min-height: 550px;
  right: -300px;
  z-index: -1;
}

.wow {
  position: absolute;
  min-height: 550px;
  right: -355px;
  z-index: -1;
}

.diabloHD {
  position: absolute;
  min-height: 550px;
  right: -800px;
  z-index: -1;
}

.starcraft {
  position: absolute;
  min-height: 550px;
  right: -950px;
  z-index: -1;
}

.default {
  position: absolute;
  opacity: 0;
  min-height: 550px;
  right: -250px;
}
</style>