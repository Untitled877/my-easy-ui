<demo>
常规使用
</demo>
<template>
  <Input placeholder="请输入内容" v-model:value="text"/>
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

