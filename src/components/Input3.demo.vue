<demo>
支持禁用
</demo>
<template>
  <Input disabled v-model:value="text"/>
</template>

<script lang="ts">
import Input from '../lib/Input.vue';
import {ref} from 'vue';

export default {
  components: {
    Input
  },
  setup(props) {
    const text = ref('');
    return {text};
  }
};
</script>

