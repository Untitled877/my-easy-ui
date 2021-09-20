<demo>
密码框
</demo>
<template>
  <Input placeholder="请输入密码" type="password" v-model:value="text"/>
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

