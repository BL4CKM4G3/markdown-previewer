<template>
  <div class="preview">
    <div v-html="markdownToHtml"></div>
  </div>
</template>

<script>
import marked from 'marked'

export default {
  name: 'Preview',
  props: ['markdown'],
  computed: {
    markdownToHtml() {
      return marked(this.markdown)
    }
  }
}
</script>

<style>
.preview {
  width: 40vw;
  height: 80vh;
  background-color: white;
  overflow-y: scroll;
}
</style>