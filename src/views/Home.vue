<template>
  <div class="home">
    <h1 class="heading">Markdown Previewer 1.0</h1>
    <div class="d-flex row j-around">
      <div class="d-flex col editor-wrapper">
        <p class="caption">Editor</p>
        <MonacoEditor
          width="500"
          height="80vh"
          theme="vs-dark"
          language="markdown"
          :options="options"
          v-model="text"
        ></MonacoEditor>
      </div>
      <div class="d-flex col preview-wrapper">
        <p class="caption">Preview</p>
        <preview :markdown="text"></preview>
      </div>
    </div>
  </div>
</template>

<script>
import MonacoEditor from 'monaco-editor-vue'
import Preview from '../components/Preview.vue'
// @ is an alias to /src

export default {
  name: 'Home',
  components: {
    MonacoEditor,
    Preview
  },
  data: () => ({
    text: '',
    options: {

    }
  })
}
</script>

<style lang="scss" scoped>
.home {
  display: flex;
  flex-direction: column;
  h1 {
    text-align: center;
  }
}

.editor-wrapper, .preview-wrapper {
  padding-top: 25px;
  p {
    margin-bottom: 5px;
  }
}
</style>
