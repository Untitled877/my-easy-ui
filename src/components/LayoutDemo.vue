<template>
  <div>
    <h1>Layout 示例</h1>
    <Demo :component="Layout1Demo" />
    <Attr :columns="columns" :data="data"/>
  </div>
</template>

<script lang="ts">
import Demo from "./Demo.vue";
import Layout1Demo from "./Layout1.demo.vue";
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
    ]);
    return {
      Layout1Demo,
      columns,
      data
    };
  },
};
</script>
