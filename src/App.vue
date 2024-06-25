<template>
  <RouterView v-slot="{ Component }">
    <Suspense timeout="0">
      <template #default>
        <component :is="Component" :key="$route.path"></component>
      </template>
      <template #fallback>
        <VLoading />
      </template>
    </Suspense>
  </RouterView>
</template>

<script setup>
import VLoading from '@/components/Loading.vue'
</script>

<style lang="scss">
html {
  font-size: 62.5%;
  box-sizing: border-box;
  scroll-behavior: smooth;
}

body {
  font-family: 'Comic Relief', sans-serif;
  color: $indigo-100;
  overflow-x: hidden;
}

::selection {
  background-color: $indigo-400;
  color: $gray-400;
}
</style>
