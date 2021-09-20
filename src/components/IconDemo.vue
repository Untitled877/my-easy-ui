<template>
  <div>
    <h1>Icon 示例</h1>
    <Demo :component="IconDemo" />
    <Attr :columns="columns" :data="data"/>
  </div>
</template>

<script lang="ts">
import Demo from "./Demo.vue";
import IconDemo from "./Icon.demo.vue";
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
        attrs: 'name',
        explain: 'Icon名字',
        type: 'string',
        select: '-',
        default: '-',
      },
    ]);
    return {
      IconDemo,
      columns,
      data
    };
  },
};
</script>
