<script setup>
defineProps({ src: String })
</script>

<template>
  <div class="img-wrapper">
    <img :src="src" alt="" class="img-square fade-in" />
  </div>
</template>
