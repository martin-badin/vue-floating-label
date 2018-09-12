<template>
  <div id="app">
    <floating-label label="Label">
      <input value="">
    </floating-label>
    <floating-label label="Label">
      <select>
        <option value="">Default</option>
        <option value="aa">AA</option>
      </select>
    </floating-label>
    <floating-label label="Label">
      <textarea></textarea>
    </floating-label>
    <floating-label label="Label" disabled>
      <input type="file">
    </floating-label>
  </div>
</template>

<script>
import { FloatingLabel } from "./components";

export default {
  name: "app",
  components: {
    FloatingLabel
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

input,
select,
textarea {
  display: block;
  border: 1px solid black;
  border-radius: 3px;
  height: 40px;
  width: 100%;
}
</style>