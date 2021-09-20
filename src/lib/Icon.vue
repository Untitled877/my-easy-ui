<template>
  <svg class="easy-icon" aria-hidden="true">
    <use :xlink:href="`#icon-${name}`"></use>
  </svg>
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
.easy-icon {
  width: 1.5em;
  height: 1.5em;
  fill: currentColor;
}

</style>