<demo>
常规使用
</demo>
<template>
  <div class="icons">
    <Icon name="over"></Icon>
    <Icon name="menu-manage"></Icon>
    <Icon name="link"></Icon>
    <Icon name="cancel"></Icon>
    <Icon name="daogang"></Icon>
    <Icon name="yuyin"></Icon>
    <Icon name="manager"></Icon>
    <Icon name="log"></Icon>
    <Icon name="warning"></Icon>
    <Icon name="search"></Icon>
  </div>
</template>

<script lang="ts">
import Icon from '../lib/Icon.vue';

export default {
  components: {
    Icon
  }
};
</script>

<style lang="scss" scoped>
.icons {
  svg {
    margin-right: 10px
  }
}
</style>
