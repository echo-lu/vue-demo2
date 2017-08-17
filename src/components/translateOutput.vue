<template>
  <div id="translateOutput">
    <h2>{{ translatedText }}</h2>
  </div>
</template>

<script>
export default {
  name: 'translateOutput',
  props: [
    "translatedText"
  ],
  methods: {
    formSubmit(e) {
      this.$emit("formSubmit",this.textToTranslate)
      e.preventDefault();
    }
  }
}
</script>


