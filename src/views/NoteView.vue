<template>
  <div class="container">
    <div class="ql-edit-wrap">
      <QuillEditor />
    </div>
    <div class="preview-wrap">
      <h2>Preview</h2>
      <div class="preview">
        <p>this is preview</p>
      </div>
    </div>
  </div>
</template>
<script>
import { QuillEditor } from '@vueup/vue-quill'
import '@vueup/vue-quill/dist/vue-quill.snow.css'
export default {
  components: {
    QuillEditor
  }
}
</script>
<style scoped>
.container {
  max-width: 1440px;
  margin: 0 auto;
  display: flex;
  gap: 40px;
  padding: 100px 20px;
}
.ql-edit-wrap, 
.preview-wrap {
  flex: 1 0 0;
}
</style>
