<template>
  <div class="loading">
    <div class="loading__circle"></div>
    <p class="loading__text">Please wait</p>
  </div>
</template>

<script setup></script>

<style lang="scss" scoped>
.loading {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100dvh;
  background-color: $gray-500;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  gap: 2rem;

  &__circle {
    position: relative;
    width: 7.5rem;
    height: 7.5rem;
    color: $indigo-600;
    display: inline-block;
    box-sizing: content-box;
    animation: loading-cycle 1s infinite linear;

    &::after {
      content: ' ';
      display: block;
      width: 15em;
      height: 15em;
      box-sizing: border-box;
      transform-origin: 0 0;
      transform: translateZ(0) scale(0.5);
      backface-visibility: hidden;
      border-radius: 50%;
      border: 1em solid currentColor;
      border-left-color: transparent;
    }
  }

  &__text {
    @include typography(paragraph-1);
  }
}
</style>