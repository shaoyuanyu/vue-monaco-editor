<script setup lang="ts">
import Editor from '@/components/code_editor/CodeEditor.vue'
// models
import type { Appearance } from "@/components/code_editor/models/appearance"

const currentLang = 'c'
const appearance: Appearance = {
  isDark: true,
  fontSize: 16
}
</script>

<template>
  <div style="width: 80%; height: 100vh; padding: 20px 20px; background-color: antiquewhite">
    <Editor :language="currentLang" :appearance="appearance" />
  </div>
</template>

<style scoped></style>
