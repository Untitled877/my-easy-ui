<template>
  <span class="easy-icon-wrapper">
    <svg class="easy-icon" aria-hidden="true">
      <use :xlink:href="`#icon-${name}`"></use>
    </svg>
  </span>
</template>

<script lang="ts">

export default {
  props: {
    name: {
      type: String,
    },
  },
};
</script>

<style lang="scss">
.easy-icon-wrapper {
  width: 1.5em;
  height: 1.5em;
  display: inline-flex;
  justify-content: center;
  align-items: center;
  .easy-icon {
    fill: currentColor;
    width: 100%;
    height: 100%;
  }
}
</style>