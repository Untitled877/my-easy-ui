<template>
<div>
  <h1>Button 示例</h1>
  <Demo :component="Button1Demo" />
  <Demo :component="Button2Demo" />
  <Demo :component="Button3Demo" />
  <Demo :component="Button4Demo" />
  <Attr :columns="columns" :data="data"/>
</div>
</template>

<script lang="ts">
import Demo from "./Demo.vue";
import Button1Demo from "./Button1.demo.vue";
import Button2Demo from "./Button2.demo.vue";
import Button3Demo from "./Button3.demo.vue";
import Button4Demo from "./Button4.demo.vue";
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
        attrs: 'theme',
        explain: '按钮样式',
        type: 'string',
        select: 'button/main/text/link/danger',
        default: 'button',
      },
      {
        attrs: 'size',
        explain: '按钮尺寸',
        type: 'string',
        select: 'small/normal/big',
        default: 'normal',
      },
      {
        attrs: 'disabled',
        explain: '是否禁用',
        type: 'boolean',
        select: 'disabled / -',
        default: '-',
      },
      {
        attrs: 'loading',
        explain: '是否加载',
        type: 'boolean',
        select: 'loading / -',
        default: '-',
      }
    ]);
    return {
      Button1Demo,
      Button2Demo,
      Button3Demo,
      Button4Demo,
      columns,
      data
    };
  },
};
</script>
