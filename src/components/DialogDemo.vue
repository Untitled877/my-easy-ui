<template>
<h1>Dialog 示例</h1>
<Demo :component="Dialog1Demo" />
<Demo :component="Dialog2Demo" />
  <Attr :columns="columns" :data="data"/>
</template>

<script lang="ts">
import Demo from './Demo.vue';
import Dialog1Demo from './Dialog1.demo.vue';
import Dialog2Demo from './Dialog2.demo.vue';
import Attr from "./Attr.vue";
import {columns} from '../lib/data';
import {ref} from 'vue';
export default {
  components: {
    Demo,
    Attr
  },
  setup() {
    const data = ref([
      {
        attrs: 'visible',
        explain: '是否展示',
        type: 'boolean',
        select: 'true/false',
        default: 'false',
      },
      {
        attrs: 'closeOnClickOverlay',
        explain: '点击遮罩层是否关闭',
        type: 'boolean',
        select: 'true/false',
        default: 'false',
      },
      {
        attrs: 'ok',
        explain: '点击确认触发函数',
        type: 'function',
        select: '-',
        default: '-',
      },
      {
        attrs: 'cancel',
        explain: '点击取消触发函数',
        type: 'function',
        select: '-',
        default: '-',
      }
    ]);
    return {
      Dialog1Demo,
      Dialog2Demo,
      columns,
      data
    }
  }
}
</script>
