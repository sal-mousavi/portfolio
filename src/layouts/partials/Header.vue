<template>
  <header class="header">
    <nav class="header__nav">
      <a href="#" class="header__nav-link">Home</a>
      <a href="#skills" class="header__nav-link">Skills</a>
      <a href="#projects" class="header__nav-link">Projects</a>
      <a href="#contact" class="header__nav-link">Contact</a>
    </nav>
  </header>
</template>

<script setup></script>

<style lang="scss" scoped>
.header {
  background-color: $gray-300;
  border-radius: 50px;
  position: fixed;
  top: 2.4rem;
  left: 50%;
  transform: translateX(-50%);
  padding: 0.2rem;
  z-index: 1000;

  &__nav {
    display: flex;
  }

  &__nav-link {
    font-size: 1.6rem;
    color: inherit;
    padding: 0.8rem 1.6rem;
    text-decoration: none;
    transition: $slow-transition;
    border-radius: 50px;

    @include respond-to(small) {
      font-size: 1.8rem;
    }

    &:hover {
      background-color: $gray-500;
    }
  }
}
</style>
