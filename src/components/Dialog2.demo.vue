<demo>
调用函数打开 Dialog
</demo>
<template>
  <div>
    <Button @click="showDialog">打开对话框</Button>
  </div>
</template>

<script lang="ts">
import Button from '../lib/Button.vue';
import {h} from 'vue';
import { openDialog} from '../lib/openDialog';

export default {
  components: {Button},
  setup() {
    const showDialog = () => {
      openDialog({
        title: h('strong', {}, '标题'),
        content: '正文部分',
        closeOnClickOverlay: false,
        ok() {
          console.log('OK')
        },
        cancel() {
          console.log('cancel')
        }
      })
    };
    return {showDialog};
  }
};

</script>