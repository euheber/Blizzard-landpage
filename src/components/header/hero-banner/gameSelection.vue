<template>
  <div class="game-selection">
    <h1>Retorne à escuridão com o game Diablo IV</h1>
    <p>O retorno de Lilith traz uma era de escuridão e sofrimento.</p>

    <button>Jogue agora</button>
  </div>
  <selectGameIconVue />
</template>

<script>
import selectGameIconVue from './selectGameIcon.vue';
export default {
  name: 'GameSelection',
  components:{selectGameIconVue,}
}
</script>

<style lang="scss" scoped>
$text-color: white;
$button-bg: #00AEFF;

.game-selection {
  width: 283px;
  margin: 51px 70px 0px 22px;

  h1,
  p {
    color: $text-color;
    text-align: left;
  }

  ;

  h1 {
    font-size: 40px;
    line-height: 44px;
    margin-bottom: 1rem;
  }

  ;

  p {
    margin-bottom: 2rem;
    font-size: 16px;
    font-weight: 400;
    line-height: 27px;
    letter-spacing: -0.005em;
    font-style: normal;
  }

  ;

  button {
    width: 10.5rem;
    height: 3.25rem;
    background-color: $button-bg;
    border-radius: 4px;
    padding: 14px 32px;
    color: $text-color;
  }
}

ul {
    display: flex;
    gap: 1rem;
    margin: 48px 49px 68px 22px;

    img {
        width: 48px;
        height: 48px;
    }
}

</style>