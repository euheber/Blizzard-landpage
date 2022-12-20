<template>
  <div class="game-selection">
    <selectGameIconVue @getData="gotData" class="testeD" />

    <div class="position-relative-container">
      <div class="position-absolute-container">
        <h1>{{ title }}</h1>
        <p>{{ description }}</p>
        <button>{{ cta }}</button>
      </div>
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
  }),
  methods: {
    gotData({ title, bg, description, cta, highlight, divider }) {
      this.title = title
      this.background = bg
      this.description = description
      this.cta = cta

      this.$emit('getBg', { bg, highlight, divider })
    }
  }
}
</script>

<style src="../../../assets/scss/header/gameSelection.scss" lang="scss" scoped />
