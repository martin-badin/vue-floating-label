<template>
  <div class="floating-label">
    <div class="floating-label--inner">
      <span :class="{
        'floating-label--label': true,
        'floating-label--label__top': showOnTop
      }">{{ label }}</span>
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: "FloatingLabel",
  props: {
    label: {
      type: String,
      required: true
    },
    showOnTop: {
      type: Boolean,
      default: false
    }
  }
};
</script>

<style lang="scss">
.floating-label {
  padding-top: 15px;

  &--inner {
    position: relative;
  }

  &--label {
    position: absolute;
    left: 0;

    transition: all 200ms ease-in-out;

    &:not(&__top) {
      padding-left: 10px;
      padding-right: 10px;
      top: 50%;
      transform: translate(0, -50%);
    }

    &__top {
      padding-left: 0;
      padding-right: 0;
      top: 0;
      transform: translate(0, -100%);
    }
  }
}
</style>

