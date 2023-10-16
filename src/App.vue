<script setup lang="ts">
import { onBeforeUnmount, onMounted, ref } from 'vue'
import * as monaco from 'monaco-editor'

const editorContent = "#include <stdio.h>"
const language = "c"
const editorFontSize = 16
const editorTheme = ""

const editor = ref<HTMLInputElement | null>(null)
const monacoEditor = ref<monaco.editor.IStandaloneCodeEditor | null>(null)

onMounted(() => {
  monacoEditor.value = monaco.editor.create(editor.value!, {
    value: editorContent,
    language: language,
    fontSize: editorFontSize,
  })

  /*
  monaco.editor.defineTheme("test-theme", {
    base: "vs",
    colors: {},
    inherit: true,
    rules: [{
      token: ""
    }],
  })
  */

  monaco.editor.setTheme("test-theme")
})

onBeforeUnmount(() => {
  monacoEditor.value!.dispose()
})
</script>

<template>
  <div ref="editor" style="width: 100%; height: 100vh"></div>
</template>

<style scoped></style>
