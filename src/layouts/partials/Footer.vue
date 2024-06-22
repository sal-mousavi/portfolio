<template>
  <div class="footer-wrapper">
    <footer class="footer container">
      <section class="contact-section" id="contact">
        <h3 class="contact-section__title">Want to work together?</h3>
        <p class="contact-section__description">
          Feel free to reach out for collaborations or just a friendly hello
        </p>
        <div
          class="contact-section__email"
          :class="{ 'contact-section__email--copied': copyAnimationActive }"
          @click.prevent="copyToClipboard"
        >
          <span>{{ email }}</span>
          <VIcon name="icon-copy" />
        </div>
      </section>

      <div class="footer__copyright">Copyright © 2024 by SAL Mousavi. All rights reserved.</div>
    </footer>
  </div>
</template>

<script setup>
import VIcon from '@/components/Icon.vue'
import { ref } from 'vue'

const email = 'sa.laalmousavi@gmail.com'
const copyAnimationActive = ref(false)

const copyToClipboard = async () => {
  try {
    await navigator.clipboard.writeText(email)

    copyAnimationActive.value = true
    setTimeout(() => {
      copyAnimationActive.value = false
    }, 1000)
  } catch ($e) {
    alert('Can not copy')
  }
}
</script>

<style lang="scss" scoped>
.footer-wrapper {
  background-color: $gray-600;
}

.container {
  max-width: 144rem + (2 * 2rem);
  margin-inline: auto;
  padding-inline: 2rem;
}

.footer {
  padding: 4.8rem 2rem 3rem;

  &__copyright {
    @include typography(paragraph-5);
    margin-top: 4.8rem;
    text-align: center;

    @include respond-to(small) {
      margin-top: 6.4rem;
    }

    @include respond-to(medium) {
      margin-top: 12.8rem;
    }
  }
}

.contact-section {
  &__title {
    @include typography(headline-3);
    margin-bottom: 1.4rem;
  }

  &__description {
    @include typography(paragraph-1);
    margin-bottom: 1.8rem;
  }

  &__email {
    position: relative;
    overflow: hidden;
    @include typography(paragraph-1);
    padding: 0.9rem 2rem;
    border-radius: 50px;
    display: inline-flex;
    align-items: center;
    gap: 2rem;
    background-color: rgba($indigo-600, 50%);
    cursor: pointer;

    &:hover {
      box-shadow: 0 0 1rem $indigo-100;
    }

    & * {
      z-index: 2;
    }

    & svg {
      height: 1em;
    }

    &--copied {
      &::after {
        content: '';
        animation: slide 1s ease-in-out;
        background-image: linear-gradient(90deg, #28a745 50%, transparent 50%);
        bottom: 0;
        left: -50%;
        opacity: 0.8;
        position: absolute;
        right: -50%;
        top: 0;
        z-index: 1;
      }
    }
  }
}
</style>
