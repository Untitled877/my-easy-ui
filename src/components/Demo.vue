<template>
<div class="demo">
  <h2>{{component.__sourceCodeTitle}}</h2>
  <div class="demo-component">
    <component :is="component" />
  </div>
  <div class="demo-actions">
    <Button theme="text" @click="hideCode" v-if="codeVisible">隐藏代码</Button>
    <Button theme="text" @click="showCode" v-else>查看代码</Button>
  </div>
  <div class="demo-code" v-if="codeVisible">
    <pre v-html="html" />
  </div>

</div>
</template>

<script lang="ts">
import Button from '../lib/Button.vue'
import 'prismjs';
import 'prismjs/themes/prism.css'
import {
  computed,
  ref
} from 'vue';
const Prism = (window as any).Prism
export default {
  components: {
    Button
  },
  props: {
    component: Object
  },
  setup(props) {
    const html = computed(() => {
      return Prism.highlight(props.component.__sourceCode, Prism.languages.html, 'html')
    })
    const showCode = () => codeVisible.value = true
    const hideCode = () => codeVisible.value = false
    const codeVisible = ref(false)
    return {
      Prism,
      html,
      codeVisible,
      showCode,
      hideCode
    }
  }
}
</script>

<style lang="scss" scoped>
$border-color: #004935;
$border-radius: 4px;

.demo {
  border: 1px solid $border-color;
  border-radius: $border-radius;
  margin: 16px 0 32px;

  >h2 {
    font-size: 20px;
    padding: 8px 16px;
    border-bottom: 1px solid $border-color;
  }

  &-component {
    padding: 16px;
  }

  &-actions {
    padding: 8px 16px;
    border-top: 1px dashed $border-color;
  }

  &-code {
    overflow-x: auto;
    padding: 8px 16px;
    border-top: 1px dashed $border-color;

    >pre {
      line-height: 1.1;
      font-family: Consolas, 'Courier New', Courier, monospace;
      margin: 0;
    }
  }
}
</style>
