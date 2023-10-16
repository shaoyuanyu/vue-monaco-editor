<script setup lang="ts">
import Editor from '@/components/code_editor/CodeEditor.vue'

const currentLang = 'c'

</script>

<template>
  <div style="width: 80%; height: 100vh; padding: 20px 20px; background-color: antiquewhite">
    <Editor :language="currentLang" :is-dark="false" />
  </div>
</template>

<style scoped></style>
