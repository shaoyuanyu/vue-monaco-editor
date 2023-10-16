<script setup lang="ts">
import Editor from '@/components/Editor.vue'
import { useStorage } from '@vueuse/core'
import { StorageName } from '@/utils'
import { ref } from 'vue'

const items = ref([
  { text: 'HTML', value: 'html' },
  { text: 'CSS', value: 'css' },
  { text: 'JS', value: 'javascript' }
])

const currentTab = useStorage(StorageName.ACTIVE_TAB, items.value[0].value)
</script>

<template>
  <div style="width: 80%; height: 100vh; padding: 20px 20px; background-color: antiquewhite">
    <Editor :active-tab="currentTab" />
  </div>
</template>

<style scoped></style>
