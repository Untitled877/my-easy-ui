<demo>
常规使用
</demo>
<template>
  <Layout className="layout">
    <Header className="x">header</Header>
    <Content className="y">content</Content>
    <Footer className="x">footer</Footer>
  </Layout>
</template>

<script lang="ts">
import Layout, {Header, Content, Footer} from '../lib/Layout.vue';

export default {
  components: {
    Layout,
    Header,
    Content,
    Footer
  }
};
</script>
