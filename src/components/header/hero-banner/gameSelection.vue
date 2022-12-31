<template>
  <div class="game-selection">
   <div class="position-relative-container">
       <div class="position-absolute-container">
            <h1>{{ title }}</h1>
            <p>{{ description }}</p>
            <button>{{ cta }}</button>
       </div>
    <selectGameIconVue @getData="gotData" />
  </div>


    <div id="logo-gif">
      <img :src="logo" :alt="alt" class="logo">
      <img :src="gif" :alt="alt" class="gif">
    </div>
  </div>
</template>

<script>
import selectGameIconVue from './selectGameIcon.vue';
export default {
  name: 'GameSelection',
  components: { selectGameIconVue },
  data: () => ({
    title: 'Retorne à escuridão com o game Diablo IV',
    description: 'O retorno de Lilith traz uma era de escuridão e sofrimento',
    cta: 'Jogue agora',
    logo: 'icons-banner-hero/diabloLogo.svg',
    gif: 'icons-banner-hero/diabloIV.gif',
    alt: 'Diablo IV'
  }),
  methods: {
    gotData({ title, bg, description, cta, highlight, divider, logo, gif, alt}) {
      this.title = title
      this.description = description
      this.cta = cta
      this.logo = logo,
      this.gif = gif
      this.alt = alt
      this.$emit('getBg', { bg, highlight, divider })
    }
  }
}
</script>



<style src="../../../assets/scss/header/gameSelection.scss" lang="scss" scoped />
