<template>
  <HeaderLayout />
  <main class="main">
    <div class="hero-section-wrapper">
      <section class="hero-section container">
        <div class="hero-section__text-box">
          <span class="hero-section__greeting">Hello</span>
          <h1 class="hero-section__heading">
            I'm SAL Mousavi A Front&#8209;End Developer and Designer
          </h1>
        </div>
        <div class="hero-section__img-box">
          <img src="@/assets/images/astronaut.jpeg" alt="Astronaut working with laptop" />
        </div>
      </section>
    </div>

    <section class="skills-section container" id="skills">
      <h2 class="skills-section__heading">- My Skillset -</h2>

      <div class="skills">
        <div
          class="skills__skill-text-box skills__skill-text-box--vue"
          :class="{ 'skills__skill-text-box--visible': activeSkill === 'vue' }"
        >
          <p class="skills__skill-title">Vue.js</p>
          <p class="skills__skill-description">
            Creating SPAs with Vue Router and managing state with Pinia. Proficient in the
            Composition API and integrating various libraries to enhance user experience and
            application performance.
          </p>
        </div>
        <div
          class="skills__skill-img-box skills__skill-img-box--vue"
          :class="{ 'skills__skill-img-box--active': activeSkill === 'vue' }"
          @mouseenter="activeSkill = 'vue'"
        >
          <VIcon class="skills__skill-icon" name="icon-vue" />
        </div>

        <div
          class="skills__skill-img-box skills__skill-img-box--javascript"
          :class="{ 'skills__skill-img-box--active': activeSkill === 'javascript' }"
          @mouseenter="activeSkill = 'javascript'"
        >
          <VIcon class="skills__skill-icon" name="icon-javascript" />
        </div>
        <div
          class="skills__skill-text-box skills__skill-text-box--javascript"
          :class="{ 'skills__skill-text-box--visible': activeSkill === 'javascript' }"
        >
          <p class="skills__skill-title">JavaScript</p>
          <p class="skills__skill-description">
            Creating scalable web applications by leveraging advanced JavaScript features and OOP
            techniques to produce clean, modular, and reusable code.
          </p>
        </div>

        <div
          class="skills__skill-text-box skills__skill-text-box--sass"
          :class="{ 'skills__skill-text-box--visible': activeSkill === 'sass' }"
        >
          <p class="skills__skill-title">Sass & Css</p>
          <p class="skills__skill-description">
            Crafting efficient and maintainable front-end systems with a focus on styling and
            animations. Adhering to BEM methodology, and employing the 7-1 architecture pattern.
          </p>
        </div>
        <div
          class="skills__skill-img-box skills__skill-img-box--sass"
          :class="{ 'skills__skill-img-box--active': activeSkill === 'sass' }"
          @mouseenter="activeSkill = 'sass'"
        >
          <VIcon class="skills__skill-icon" name="icon-sass" />
        </div>

        <div
          class="skills__skill-img-box skills__skill-img-box--figma"
          :class="{ 'skills__skill-img-box--active': activeSkill === 'figma' }"
          @mouseenter="activeSkill = 'figma'"
        >
          <VIcon class="skills__skill-icon" name="icon-figma" />
        </div>
        <div
          class="skills__skill-text-box skills__skill-text-box--figma"
          :class="{ 'skills__skill-text-box--visible': activeSkill === 'figma' }"
        >
          <p class="skills__skill-title">Figma & Design</p>
          <p class="skills__skill-description">
            Creating high-fidelity designs and prototypes. Skilled in developing component-based
            design systems that ensure consistency and efficiency across products.
          </p>
        </div>

        <div
          class="skills__skill-text-box skills__skill-text-box--html"
          :class="{ 'skills__skill-text-box--visible': activeSkill === 'html' }"
        >
          <p class="skills__skill-title">HTML</p>
          <p class="skills__skill-description">
            Using semantic markup to enhance accessibility and SEO. Skilled in crafting
            well-structured and standards-compliant web pages.
          </p>
        </div>
        <div
          class="skills__skill-img-box skills__skill-img-box--html"
          :class="{ 'skills__skill-img-box--active': activeSkill === 'html' }"
          @mouseenter="activeSkill = 'html'"
        >
          <VIcon class="skills__skill-icon" name="icon-html" />
        </div>
      </div>
    </section>

    <section class="projects-section container" id="projects">
      <h2 class="projects-section__heading">- Projects -</h2>

      <div class="projects-section__cards-container">
        <VProjectCard>
          <template v-slot:project-logo>
            <img src="@/assets/images/bagilink-logo.png" alt="Bagilink Logo" />
          </template>
          <template v-slot:project-description>
            Bagilink is a website that allows you to share links easily. It provides a platform to
            manage and share multiple URLs through a single link, making it convenient for social
            media and website sharing.
          </template>
          <template v-slot:project-img>
            <img src="@/assets/images/bagilink-preview.png" alt="Bagilink home page preview" />
          </template>

          <template v-slot:project-btn-container>
            <VButton
              class="btn btn--primary btn--grow"
              href="https://github.com/sal-mousavi/bagilink"
              target="_blank"
            >
              <VIcon name="icon-code" />
              Source Code
            </VButton>
            <VButton
              class="btn btn--primary btn--grow"
              href="https://sal-mousavi.github.io/bagilink/#/"
              target="_blank"
            >
              <VIcon name="icon-browser" />
              Visit Website
            </VButton>
          </template>
        </VProjectCard>

        <VProjectCard>
          <template v-slot:project-logo>
            <img src="@/assets/images/podcasty-logo.png" alt="Podcasty Logo" />
          </template>
          <template v-slot:project-description>
            Podcasty is a platform that offers a wide range of podcasts and shows for streaming.
            It's a great place to find and listen to the latest episodes from top podcasts, covering
            various topics like news, sports, and lifestyle.
          </template>
          <template v-slot:project-img>
            <img src="@/assets/images/podcasty-preview.png" alt="Podcasty home page preview" />
          </template>

          <template v-slot:project-btn-container>
            <VButton
              class="btn btn--primary btn--grow"
              href="https://www.figma.com/design/Qqe5KDlioFqsucltU2jx0k/Podcast?node-id=66-2&t=dOB7GPBotgG0EIGt-1"
              target="_blank"
            >
              <VIcon name="icon-figma" />
              Figma Design
            </VButton>
          </template>
        </VProjectCard>
      </div>
    </section>
  </main>
  <FooterLayout />
</template>

<script setup>
import HeaderLayout from '@/layouts/partials/Header.vue'
import FooterLayout from '@/layouts/partials/Footer.vue'
import VIcon from '@/components/Icon.vue'
import VProjectCard from '@/components/ProjectCard.vue'
import VButton from '@/components/Button.vue'
import { ref } from 'vue'

const activeSkill = ref('vue')
</script>

<style lang="scss" scoped>
.main {
  background-color: $gray-500;
}

.container {
  max-width: 144rem + (2 * 2rem);
  margin-inline: auto;
  padding-inline: 2rem;
}

.hero-section-wrapper {
  background-image: url('@/assets/images/stardust-background.png');
}

.hero-section {
  display: grid;
  align-items: center;
  justify-items: center;
  gap: 4.8rem;
  padding: 11.1rem 2rem 3.6rem;
  text-align: center;

  @include respond-to(small) {
    padding: 13.6rem 2rem 6.4rem;
  }

  @include respond-to(medium) {
    grid-template-columns: 1fr 1fr;
    padding: clamp(11.1rem, 6.593vw + 10.507rem, 20rem) 2rem;
    text-align: left;
  }

  &__text-box {
    padding-top: 1.4rem;
    align-self: start;
  }

  &__greeting {
    @include typography(headline-2);
    color: $indigo-600;
  }

  &__heading {
    @include typography(headline-1);
  }

  &__img-box {
    & > img {
      max-width: 100%;
      width: 25.6rem;
      border-radius: 50px;
      border: 5px solid $indigo-600;

      @include respond-to(small) {
        width: 34.1rem;
      }

      @include respond-to(medium) {
        width: clamp(34.1rem, 12.574vw + 33.094rem, 51.2rem);
      }
    }
  }
}

.skills-section {
  padding: 4.8rem 2rem;
  display: flex;
  flex-direction: column;
  align-items: center;

  @include respond-to(medium) {
    padding: 9.6rem 2rem;
  }

  &__heading {
    @include typography(headline-1);
    color: $indigo-600;
    margin-bottom: 3.6rem;

    @include respond-to(medium) {
      margin-bottom: 9.6rem;
    }

    @include respond-to(medium) {
      margin-bottom: 12.8rem;
    }
  }
}

.skills {
  display: grid;
  grid-template-columns: auto 1fr auto;
  align-items: center;
  column-gap: 2.4rem;
  max-width: 50rem;

  @include respond-to(medium) {
    max-width: 90rem;
    grid-template-columns: 3fr 6fr 3fr;
    place-items: center;
    gap: 6.4rem;
  }

  @include respond-to(large) {
    max-width: 144rem;
    gap: 9.6rem;
  }

  &__skill-text-box {
    position: relative;
    padding-block: 2.7rem;
    grid-column: span 2;

    @include respond-to(medium) {
      display: flex;
      visibility: hidden;
      flex-direction: column;
      gap: 2.4rem;
      align-items: center;
      text-align: center;
      grid-column: 2;
      grid-row: 2;
      height: 30.9rem;
      padding: 8.1rem 2rem;

      &--visible {
        visibility: visible;
      }
    }

    @include respond-to(large) {
      height: 46.4rem;
      padding: 13rem 12rem 0;
    }

    &::before {
      content: '';
      position: absolute;
      left: 0;
      top: 50%;
      transform: translateY(-50%);
      width: 15rem;
      height: 15rem;
      border-radius: 50rem;
      background-color: rgba($indigo-600, 50%);
      filter: blur(15rem);

      @include respond-to(medium) {
        width: 30.9rem;
        height: 30.9rem;
        left: 50%;
        transform: translate(-50%, -50%);
      }

      @include respond-to(large) {
        width: 46.4rem;
        height: 46.4rem;
      }
    }
  }

  &__skill-title {
    @include typography(paragraph-1);
    margin-bottom: 0.3rem;
  }

  &__skill-description {
    @include typography(paragraph-3);
  }

  &__skill-img-box {
    width: 9.6rem;
    height: 9.6rem;
    border: 0.4rem solid $gray-400;
    border-radius: 20px;
    display: grid;
    place-items: center;
    z-index: 10;

    @include respond-to(medium) {
      width: 14.6rem;
      height: 14.6rem;
      transition: $default-transition;

      &--active {
        box-shadow: 0 0 2rem $indigo-400;
      }
    }

    @include respond-to(large) {
      width: 22rem;
      height: 22rem;
    }

    &--vue {
      background-color: rgba($vue, 10%);
      border-color: $vue;

      @include respond-to(medium) {
        grid-column: 2;
        grid-row: 1;
      }
    }

    &--javascript {
      background-color: rgba($javascript, 10%);
      border-color: $javascript;

      @include respond-to(medium) {
        grid-column: 3;
        grid-row: 1;
        transform: translate(-12rem, 7rem) rotate(45deg);
      }

      @include respond-to(large) {
        transform: translate(-21rem, 11rem) rotate(45deg);
      }

      & > svg {
        border-radius: 8px;
      }
    }

    &--sass {
      background-color: rgba($sass, 10%);
      border-color: $sass;

      @include respond-to(medium) {
        grid-column: 1;
        grid-row: 1;
        transform: translate(12rem, 7rem) rotate(-45deg);
      }

      @include respond-to(large) {
        transform: translate(21rem, 11rem) rotate(-45deg);
      }
    }

    &--figma {
      background-color: rgba($figma, 10%);
      border-color: $figma;

      @include respond-to(medium) {
        grid-column: 3;
        grid-row: 2;
        transform: rotate(90deg);
        justify-self: start;
      }

      @include respond-to(large) {
        justify-self: start;
      }
    }

    &--html {
      background-color: rgba($html, 10%);
      border-color: $html;

      @include respond-to(medium) {
        grid-column: 1;
        grid-row: 2;
        transform: rotate(-90deg);
        justify-self: end;
      }
    }
  }

  &__skill-icon {
    width: 4.8rem;

    @include respond-to(medium) {
      width: 6.4rem;
    }

    @include respond-to(large) {
      width: 9.8rem;
    }
  }
}

.projects-section {
  padding: 4.8rem 2rem;

  @include respond-to(small) {
    padding: 9.6rem 2rem;
  }

  @include respond-to(small) {
    padding: 12.8rem 2rem;
  }

  &__heading {
    @include typography(headline-1);
    color: $indigo-600;
    text-align: center;
    margin-bottom: 3.6rem;

    @include respond-to(small) {
      margin-bottom: 6.4rem;
    }

    @include respond-to(small) {
      margin-bottom: 9.6rem;
    }
  }

  &__cards-container {
    display: grid;
    gap: 2.4rem;

    @include respond-to(medium) {
      grid-template-columns: 1fr 1fr;
    }
  }
}
</style>
