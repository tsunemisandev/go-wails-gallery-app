<script lang="ts" setup>
import { reactive, onMounted, ref, Ref } from 'vue'
import { GetURLList } from '../../wailsjs/go/main/App'
import Image from './Image.vue'

const data = reactive({ urls: Array<string>() })
onMounted(() => getUrlList())

function getUrlList() {
  GetURLList().then((result) => {
    data.urls = result
  })
}
</script>

<template>
  <div class="grid-container">
    <Image
      v-for="(imageUrl, index) in data.urls"
      :url="imageUrl"
      :key="index"
      :width="400"
    ></Image>
  </div>
</template>

<style scoped>
.grid-container {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-gap: 2px;
}
</style>
