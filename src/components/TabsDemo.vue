<template>
<h1>Tabs 示例</h1>
<Demo :component="Tabs1Demo" />
  <Attr :columns="columns" :data="data"/>
</template>

<script lang="ts">
import Demo from './Demo.vue'
import Tabs1Demo from './Tabs1.demo.vue'
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
        attrs: 'selected',
        explain: '用于 Tabs 标签， 用来标记默认选中的 Tab',
        type: 'string',
        select: '-',
        default: '-',
      },
      {
        attrs: 'title',
        explain: '用于 Tab 标签，表示导航名称',
        type: 'string',
        select: '-',
        default: '-',
      }
    ]);
    return {
      Tabs1Demo,
      columns,
      data
    }
  }
}
</script>
