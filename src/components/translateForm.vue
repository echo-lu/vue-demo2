<template>
  <div id="translateForm" class="container">
    <div>
      <form v-on:submit="formSubmit"  class="form-inline well">
        <div class="form-group">
        <label for="tranText" class="sr-only">内容</label>
         <input type="text"  class="form-control" v-model="textToTranslate" placeholder="输入需要翻译的内容" id="tranText">
        </div>
        <select v-model="language"  class="form-control">
          <option value="en">English</option>
          <option value="ru">Russian</option>
          <option value="ko">Korean</option>
          <option value="it">Italian</option>
          <option value="ja"> Japanese</option>
        </select>
        <input type="submit" class="btn btn-primary" value="翻译">
      </form>
    </div>

  </div>
</template>

<script>
export default {
  name: 'translateForm',
  data() {
    return {
      textToTranslate:"",
      language:""
    }
  },
  methods: {
    formSubmit(e) {
      this.$emit("formSubmit",this.textToTranslate,this.language)
      e.preventDefault();
    },
    created:function() {
      this.language = "en";
    }
  }
}
</script>

<style>

</style>
