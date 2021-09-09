<template>
  <button class="easy-button" :class="classes" :disabled="disabled">
    <span v-if="loading" class="easy-loadingIndicator"></span>
    <slot/>
  </button>
</template>

<script lang="ts">
import { computed } from 'vue';

export default {
  props: {
    theme: {
      type: String,
      default: 'button',
    },
    size: {
      type: String,
      default: 'normal',
    },
    level: {
      type: String,
      default: 'normal',
    },
    disabled: {
      type: Boolean,
      default: false,
    },
    loading: {
      type: Boolean,
      default: false,
    }
  },
  setup(props) {
    const { theme, size } = props;
    const classes = computed(() => {
      return {
        [`easy-theme-${theme}`]:theme,
        [`easy-size-${size}`]:size,
      }
    });
    return { classes };
  }
};
</script>

<style lang="scss">
$h: 32px;
$color: #333;
$green: #004935;
$pink: #ffbfe0;
$radius: 4px;
$red: red;
$grey: grey;
.easy-button {
  box-sizing: border-box;
  height: $h;
  padding: 0 12px;
  cursor: pointer;
  display: inline-flex;
  justify-content: center;
  align-items: center;
  white-space: nowrap;
  background: white;
  color: $color;
  border: 1px solid $green;
  border-radius: $radius;
  box-shadow: 0 1px 0 fade-out(black, 0.95);
  transition: background 250ms;
  margin: 10px 0;
  & + & {
    margin-left: 8px;
  }
  &:hover,&:focus {
    color: lighten($green, 10%);
  }
  &:focus {
    outline: none;
  }
  &::-moz-focus-inner {
    border: 0;
  }
  &.easy-theme-main {
    background: $green;
    box-shadow: none;
    color: white;
    &:hover, &:focus {
      background: lighten($green, 10%);
    }
  }
  &.easy-theme-link {
    border-color: transparent;
    box-shadow: none;
    color: $green;
    &:hover, &:focus {
      color: lighten($green, 10%);
      text-decoration: underline;
    }
  }
  &.easy-theme-text {
    border-color: transparent;
    box-shadow: none;
    color: inherit;
    background: $pink;
    &:hover, &:focus {
      background: darken($pink, 5%);
    }
  }
  &.easy-theme-danger {
    background: $red;
    color: white;
    border-color: $red;
    &:hover, &:focus {
      background: darken($red, 10%);
      border-color: darken($red, 10%);
    }
  }
  &.easy-size-big {
    font-size: 24px;
    height: 48px;
    padding: 0 16px;
  }
  &.easy-size-small {
    font-size: 12px;
    height: 20px;
    padding: 0 4px;
  }

  &.easy-theme-button {
    &[disabled] {
      cursor: not-allowed;
      color: $grey;
      &:hover {
        border-color: $grey;
      }
    }
  }
  &.easy-theme-link, &.easy-theme-text {
    &[disabled] {
      cursor: not-allowed;
      color: $grey;
    }
  }
  > .easy-loadingIndicator {
    width: 14px;
    height: 14px;
    display: inline-block;
    margin-right: 4px;
    border-radius: 8px;
    border-color: $green $green $green transparent;
    border-style: solid;
    border-width: 2px;
    animation: easy-spin 1s infinite linear;
  }
}
@keyframes easy-spin {
  0% { transform: rotate(0deg) }
  100% { transform: rotate(360deg) }
}
</style>