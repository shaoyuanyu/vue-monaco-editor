<script setup lang="ts">
import { onBeforeUnmount, onMounted, ref } from 'vue'
import * as monaco from 'monaco-editor'

const props = defineProps({
  value: {
    type: String,
    default: ''
  },
  language: {
    type: String,
    default: 'javascript'
  }
})

const editor = ref<HTMLInputElement | null>(null)
const monacoEditor = ref<monaco.editor.IStandaloneCodeEditor | null>(null)

onMounted(() => {
  monacoEditor.value = monaco.editor.create(editor.value!, {
    value: '#include <stdio.h>',
    language: 'c',
    fontSize: 16
  })

  monaco.editor.setTheme('vs-dark')
})

onBeforeUnmount(() => {
  monacoEditor.value!.dispose()
})
</script>

<template>
  <div ref="editor" style="width: 100%; height: 100vh"></div>
</template>

<style scoped>
</style>
