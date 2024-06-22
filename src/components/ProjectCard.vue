<template>
  <div class="project-card">
    <div class="project-card__logo">
      <slot name="project-logo" />
    </div>
    <p class="project-card__description">
      <slot name="project-description" />
    </p>
    <div class="project-card__img">
      <slot name="project-img" />
    </div>

    <div class="project-card__btn-container">
      <slot name="project-btn-container" />
    </div>
  </div>
</template>

<script setup></script>

<style lang="scss" scoped>
.project-card {
  position: relative;
  background-color: $gray-400;
  border-radius: 20px;
  padding: 2rem;
  display: grid;
  justify-items: center;

  &__logo {
    height: 4rem;
    margin-bottom: 1rem;
  }

  &__description {
    @include typography(paragraph-4);
    margin-bottom: 2rem;
    text-align: center;
    
    @include respond-to(medium) {
      padding-inline: 2rem;
    }
  }

  &__img {
    align-self: flex-end;
    margin-bottom: 2rem;

    & > :slotted(img) {
      width: 100%;
    }
  }

  &__btn-container {
    justify-self: stretch;
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    padding: 1rem;
    gap: 1rem;
  }
}
</style>
