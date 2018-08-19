<template>
  <div id="app">
    <floating-label label="Label" :show-on-top="showTop">
      <input>
    </floating-label>
  </div>
</template>

<script>
import { FloatingLabel } from "./components";

export default {
  name: "app",
  components: {
    FloatingLabel
  },
  data() {
    return {
      showTop: false
    };
  },
  mounted() {
    setTimeout(() => {
      this.showTop = true;
    }, 2000);
  }
};
</script>

<style lang="scss">
.floating-label {
  &--label {
    position: absolute;
    left: 0;
    transition: all 200ms ease-in-out;

    &:not(&__top) {
      font-size: 18px;
      color: lightgray;
    }

    &__top {
      font-size: 16px;
      color: black;
    }
  }
}

input {
  display: block;
  border: 1px solid black;
  border-radius: 3px;
  height: 40px;
}
</style>