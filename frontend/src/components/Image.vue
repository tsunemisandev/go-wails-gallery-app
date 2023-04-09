<script lang="ts" setup>
import { reactive, defineProps, onMounted } from 'vue'

const data = reactive({})
const props = defineProps(['url', 'width'])
onMounted(() => console.log('Hi2'))
</script>

<template>
  <div>
    <a :href="url" target="_blank" rel="noopener noreferrer">
      <img :src="url" alt="" :style="{ width: `${width}px` }" />
    </a>
  </div>
</template>

<style scoped></style>
