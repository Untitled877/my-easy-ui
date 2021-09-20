<template>
  <div class="layout">
    <Topnav :toggle-menu-button-visible="true" class="nav"/>
    <div class="content">
      <aside v-if="menuVisible">
        <h2>文档</h2>
        <ol>
          <li>
            <router-link to="/doc/intro">介绍</router-link>
          </li>
        </ol>
        <h2>组件列表</h2>
        <ol>
          <li>
            <router-link to="/doc/icon">Icon 组件</router-link>
          </li>
          <li>
            <router-link to="/doc/switch">Switch 组件</router-link>
          </li>
          <li>
            <router-link to="/doc/button">Button 组件</router-link>
          </li>
          <li>
            <router-link to="/doc/input">Input 组件</router-link>
          </li>
          <li>
            <router-link to="/doc/dialog">Dialog 组件</router-link>
          </li>
          <li>
            <router-link to="/doc/tabs">Tabs 组件</router-link>
          </li>
          <li>
            <router-link to="/doc/layout">Layout 组件</router-link>
          </li>
        </ol>
      </aside>
      <main>
        <router-view />
      </main>
    </div>
  </div>
</template>

<script lang="ts">
import Topnav from '../components/Topnav.vue';
import {inject,Ref} from 'vue';

export default {
  components: {Topnav},
  setup() {
    const menuVisible = inject<Ref<boolean>>("menuVisible");
    return { menuVisible };
  },
};
</script>

<style lang="scss" scoped>
$green: #004935;
$pink: #ffbfe0;
$aside-index: 10;
.layout {
  display: flex;
  flex-direction: column;
  height: 100vh;
  > .nav {
    flex-shrink: 0;
  }
  > .content {
    flex-grow: 1;
    padding-top: 60px;
    padding-left: 156px;
    @media (max-width: 500px) {
      padding-left: 0;
    }
  }
  .content {
    display: flex;
    > aside {
      flex-shrink: 0;
    }
    > main {
      flex-grow: 1;
      padding: 16px;
      background: white;
    }
  }
  aside {
    background: $green;
    color: $pink;
    width: 150px;
    position: fixed;
    top: 60px;
    left: 0;
    padding: 16px 0;
    height: 100%;
    z-index: $aside-index;
    > h2 {
      margin: 8px 0;
      padding: 0 16px;
    }
    > ol {
      > li {
        > a {
          display: block;
          padding: 8px 16px;
          text-decoration: none;
          &:hover {
            background: white;
            color: $green;
          }
        }
        .router-link-active {
          background: white;
          color: $green;
        }
      }
    }
  }
  main {
    overflow: auto;
  }
}
</style>