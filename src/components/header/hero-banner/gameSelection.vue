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
  min-height: 470px;
}

.position-relative-container{
  position: relative;
  padding: 1rem;
}

.position-absolute-container{
  position: absolute;
  width: 260px;
  h1,
  p {
    color: white;
    text-align: left;
  }
  h1 {
    font-size: 36px;
    line-height: 44px;
    margin-bottom: 1rem;
  }
  p {
    margin-bottom: 1rem;
    font-size: 16px;
    font-weight: 400;
    line-height: 27px;
    letter-spacing: -0.005em;
    font-style: normal;
  }
  button {
    background-color: #00AEFF;
    border-radius: 4px;
    padding: 14px 32px;
    color: white;
  }
}

ul {
  margin: 48px 49px 22px 16px;
  flex-direction: row;
  order: 2;
  margin-top: auto;
}
</style>