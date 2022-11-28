<template>
  <header>
    <nav>
      <a href="" target="_blank">
        <img src="../assets/logo-blizzard.png" alt="Blizzard">
      </a>
      <navigation />
    </nav>
    <div class="divider"></div>
  </header>
</template>

<script>

import navigation from '../components/header/navigation.vue'
export default {
  name: 'Home',
  components: {
    navigation
  }
}
</script>
<style lang="scss" scoped>
header {
  min-height: 625px;
  width: 100%;
  background-image: url('../assets/bg-banners/bg-banner-diablo.jpg');
  background-position: center right -550px;
  background-size: cover;
  background-repeat: no-repeat;
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
</style>