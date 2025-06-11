<script setup>
import { ref, onMounted } from 'vue'
import { onTTFB, onFCP, onLCP } from 'web-vitals'

const TTFB = ref(null)
const FCP = ref(null)
const LCP = ref(null)

onMounted(() => {
  onTTFB((metric) => (TTFB.value = metric.value.toFixed(2) + ' ms'))
  onFCP((metric) => (FCP.value = metric.value.toFixed(2) + ' ms'))
  onLCP((metric) => (LCP.value = metric.value.toFixed(2) + ' ms'))
})
</script>
<template>
  <div class="flex-col-justify-between">
    Informations à propos de l'app - Vue
    <div>TTFB : {{ TTFB }}</div>
    <div>FCP : {{ FCP }}</div>
    <div>LCP : {{ LCP }}</div>
    <div>TTI : via Lighthouse</div>
    <div>TBT : via Lighthouse</div>
  </div>
</template>
