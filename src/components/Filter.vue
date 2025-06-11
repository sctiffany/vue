<script setup>
const props = defineProps({
  order: String,
  setOrder: Function,
})

const handleChange = (e) => {
  props.setOrder(e.target.value)
}
</script>

<template>
  <select :value="order" @change="handleChange" class="selectFilter">
    <option value="" disabled hidden>Filtres</option>
    <option value="asc">Trier : 1 - 800</option>
    <option value="desc">Trier : 800 - 1</option>
  </select>
</template>
