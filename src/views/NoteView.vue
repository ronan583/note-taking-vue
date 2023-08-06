<template>
  <div class="container">
    <div class="operate-wrap">
      <button class="ops" @click="clearQuillContent">Clear Content</button>
      <button class="ops" @click="showLocalStorage">ShowLocalTest</button>
    </div>
    <div class="note-container">
      <div class="ql-edit-wrap">
        <QuillEditor
          theme="snow"
          @update:content="saveQuillContent"
          v-model:content="quillContent"
          contentType="html"
          ref="quill"
        />
      </div>
      <div class="preview-wrap">
        <h2>Preview</h2>
        <div class="preview" v-html="quillContent"></div>
      </div>
    </div>
  </div>
</template>
<script setup>
import { QuillEditor } from '@vueup/vue-quill'
import '@vueup/vue-quill/dist/vue-quill.snow.css'
import { ref } from 'vue'

const CONTENT_KEY = "ql-c-key"
const TIME_INTERVAL = 800;

const quillContent = ref('')
const quill = ref()
const clearQuillContent = () => {
  quill.value.setHTML('')
}
const saveQuillContent = () => {
  
}
const startTiming = (func) => {
  const timestamp = setTimeout(func, TIME_INTERVAL);
  return timestamp;
}
const showLocalStorage = () => {
  console.log(localStorage);
}
const setLocalContent = (content) => {
  localStorage.setItem(CONTENT_KEY, content)
}
</script>
<style scoped>
.container {
  max-width: 1440px;
  margin: 0 auto;
  padding: 100px 20px;
}
.note-container {
  gap: 40px;
  display: flex;
}
.operate-wrap {
  margin-bottom: 10px;
}
.ops {
  margin-right: 10px;
}
.ql-edit-wrap,
.preview-wrap {
  flex: 1 0 0;
}
</style>
