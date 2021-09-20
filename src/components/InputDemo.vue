<template>
  <div>
    <h1>Input 示例</h1>
    <Demo :component="InputDemo1" />
    <Demo :component="InputDemo2" />
    <Demo :component="InputDemo3" />
    <Demo :component="InputDemo4" />
    <Attr :columns="columns" :data="data"/>
  </div>
</template>

<script lang="ts">
import Demo from "./Demo.vue";
import InputDemo1 from "./Input1.demo.vue";
import InputDemo2 from "./Input2.demo.vue";
import InputDemo3 from "./Input3.demo.vue";
import InputDemo4 from "./Input4.demo.vue";
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
        attrs: 'type',
        explain: '类型',
        type: 'string',
        select: '支持所有原生input类型',
        default: 'text',
      },
      {
        attrs: 'placeholder',
        explain: '提示信息',
        type: 'string',
        select: '-',
        default: '-',
      },
      {
        attrs: 'disabled',
        explain: '是否禁用',
        type: 'boolean',
        select: 'true/false',
        default: 'false',
      },
      {
        attrs: 'error-msg',
        explain: '错误提示信息',
        type: 'string',
        select: '-',
        default: '-',
      },
    ]);
    return {
      InputDemo1,
      InputDemo2,
      InputDemo3,
      InputDemo4,
      columns,
      data
    };
  },
};
</script>
