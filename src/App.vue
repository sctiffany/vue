<script setup>
import { ref, computed } from 'vue'
import Filter from './components/Filter.vue'
import PerformanceStats from './components/PerformanceStats.vue'
import ImageSquare from './components/ImageSquare.vue'

const totalImages = 800
const order = ref('asc')

const allImages = computed(() => {
  return Array.from({ length: totalImages }, (_, i) => {
    const num = order.value === 'asc' ? i + 1 : totalImages - i
    return `/assets/photo(${num}).jpg`
  })
})
</script>

<template>
  <div class="app">
    <h1>
      Quel est l’impact des optimisations modernes sur les performances web ? Étude comparative
      entre Vue.js, React et Angular à travers un benchmark synthétique
    </h1>

    <div class="infos-container">
      <div class="flex-col-justify-between">
        <img src="/assets/logo.png" class="logo" alt="logo" />
        <Filter :order="order" :setOrder="(val) => (order = val)" />
      </div>
      <PerformanceStats />
    </div>

    <div class="img-container">
      <ImageSquare v-for="(src, index) in allImages" :key="index" :src="src" />
    </div>
  </div>
</template>

<style scoped></style>
