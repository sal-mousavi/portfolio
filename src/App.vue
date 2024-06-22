<template>
  <RouterView />
</template>

<script setup></script>

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
}
</style>
