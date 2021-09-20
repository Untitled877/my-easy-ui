<demo>
错误提示
</demo>
<template>
  <Input v-model:value="text" error-msg="密码有误！"/>
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

