<script setup>
import FanyButton from './components/FanyButton.vue';
</script>

<template>

  <FanyButton>
    <template v-slot:icon="slotProps">
      {{ slotProps.hover ? '🚀' : '🍂' }}
    </template>
    <template v-slot:default>
      <strong style="text-decoration: underline;">E</strong>nviar
    </template>
  </FanyButton>
  <FanyButton>
    <template #icon="slotProps">
      {{ slotProps.hover ? '🪅' : '🐷' }}
    </template>
    <template #default>
      <strong style="text-decoration: underline;">C</strong>ancelar
    </template>
  </FanyButton>
</template>

<style scoped>
</style>