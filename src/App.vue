<template>
  <div id="app">
    <h1><strong>在线翻译</strong></h1>
    <h5 class="text-muted">简单 /易用 /便捷</h5>
    <translateForm v-on:formSubmit="translateText"></translateForm>
    <translateOutput v-text="translatedText"  class="text-success h2"></translateOutput>
  </div>
</template>

<script>
import translateForm from './components/translateForm'
import translateOutput from './components/translateOutput'

export default {
  name: 'app',
  components: {
    translateForm,
    translateOutput
  },
  data() {
    return {
      translatedText:""
    }
  },
  methods: {
    translateText(text,lang){
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20170817T074042Z.057dc18df34a7336.669dd942a3eabdfe32107c9a80bbf23fb960d17b&lang='+lang+'&text='+text)
        .then((response)=> {
          this.translatedText = response.body.text[0]
        })
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

<style>
  h2 {
    font-size: 20px;
    font-weight: bold;
  }
</style>
</style>
