<template>
  <div class="game-selection">
    <h1>{{title}}</h1>
    <p>{{description}}</p>
    <button>{{cta}}</button>
  </div>
  <selectGameIconVue @getData = "gotData" />
</template>

<script>
import selectGameIconVue from './selectGameIcon.vue';
export default {
  name: 'GameSelection',
  components:{selectGameIconVue},
  data: () => ({
      title: '',
      description: '',
      cta: '',
  }),
  methods:{
    gotData({title, bg, descripition, cta}){
        this.title = title
        this.background = bg
        this.description = descripition
        this.cta = cta
        
        this.$emit('getBg', bg)
    }
  }
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