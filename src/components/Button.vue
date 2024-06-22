<template>
  <component :is="type" class="reset" @click="onClick" :to :disabled :href>
    <slot>Button</slot>
  </component>
</template>

<script setup>
import { computed } from 'vue'

const props = defineProps({
  to: {
    type: Object,
    default: null
  },
  href: {
    type: String
  },
  onClick: {
    type: Function
  },
  disabled: {
    type: Boolean
  }
})

const type = computed(() => {
  if (props.to) return 'RouterLink'
  else if (props.href) return 'a'
  else return 'button'
})
</script>

<style lang="scss" scoped>
.reset {
  text-decoration: none;
  border: none;
  background-color: transparent;
  font-family: inherit;
  padding: 0;
  cursor: pointer;
  display: inline-flex;
  gap: 1rem;
  align-items: center;
  justify-content: center;
  text-align: center;
  text-wrap: nowrap;
}

.btn {
  font-size: 1.2rem;
  border-radius: 20px;
  padding: 0.8rem 1.2rem;
  border: 1px solid rgba($indigo-100, 50%);

  @include respond-to(small) {
    font-size: 1.4rem;
    padding: 1.2rem 1.6rem;
  }

  @include respond-to(medium) {
    font-size: 1.6rem;
    padding: 1.6rem 2.4rem;
  }

  @include respond-to(large) {
    font-size: 1.8rem;
  }

  &--primary {
    color: $indigo-100;
    background-color: $gray-400;

    &:hover {
      background-color: $gray-300;
    }
  }

  &--grow {
    flex-grow: 1;
  }

  &:disabled {
    color: $indigo-100;
    background-color: $gray-400;
    cursor: not-allowed;

    &:hover {
      background-color: unset;
    }
  }
}

:slotted(.btn > svg) {
  height: 1em;
}
</style>
