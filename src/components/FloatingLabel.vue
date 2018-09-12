<template>
  <div class="floating-label">
    <div class="floating-label--inner" ref="inner">
      <span :class="{
        'floating-label--label': true,
        'floating-label--label__top': showOnTop || !!this.value,
        'floating-label--label__align-center': align === 'center',
        'floating-label--label__align-top': align === 'top'
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
    },
    align: {
      type: String,
      default: "center",
      validate: align => ["center", "top"].indexOf(align) !== -1
    }
  },
  data() {
    return {
      value: ""
    };
  },
  methods: {
    onInput(event) {
      this.value = event.target.value;
    }
  },
  mounted() {
    this.$refs.element = this.$refs.inner.querySelector(
      "input,select,textarea"
    );
    this.value = this.$refs.element.value;
    this.$refs.element.addEventListener("input", this.onInput);
  },
  destroyed() {
    this.$refs.element.removeEventListener("input", this.onInput);
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
    }

    &__align {
      &-top {
        top: 0;
      }
      &-center {
        top: 50%;
        transform: translate(0, -50%);
      }
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