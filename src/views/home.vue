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
<style src="../assets/scss/homeComponent/home.scss" lang="scss" scoped/>
