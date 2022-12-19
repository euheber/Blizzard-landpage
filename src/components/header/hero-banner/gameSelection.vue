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

<style lang="scss" scoped>
.game-selection {
  display: flex;
  flex-direction: column;
  height: 450px;
}

.position-relative-container{
  position: relative;
  // height: 300px;
}

.position-absolute-container{
  position: absolute;
}

ul {
  margin: 48px 49px 22px 0px;
  flex-direction: row;
  order: 2;
  margin-top: auto;
}
</style>