<template>
  <div>
    <div class="topBarAndBanner">
      <Topnav/>
      <div class="banner">
        <h1>Easy UI</h1>
        <h2>一个简单的 UI 框架</h2>
        <p class="actions">
          <a href="https://github.com/Untitled877/my-easy-ui">Github</a>
          <router-link to="/doc">开始</router-link>
        </p>
      </div>
    </div>
    <div class="features">
      <ul>
        <li>
          <div class="wrapper">
            <svg class="icon">
              <use xlink:href="#icon-Vue"></use>
            </svg>
            <h3>基于 Vue 3</h3>
            <p>使用了 Vue 3 Composition API</p>
          </div>
        </li>
        <li>
          <div class="wrapper">
            <svg class="icon">
              <use xlink:href="#icon-typescript"></use>
            </svg>
            <h3>基于 TypeScript</h3>
            <p>源代码采用 TypeScript 书写</p>
          </div>
        </li>
        <li>
          <div class="wrapper">
            <svg class="icon">
              <use xlink:href="#icon-light"></use>
            </svg>
            <h3>代码易懂</h3>
            <p>每个组件的源代码都极其简洁</p>
          </div>
        </li>
      </ul>
    </div>
  </div>
</template>
<script>
import Topnav from "../components/Topnav.vue"

export default {
  components: {Topnav}
}
</script>

<style lang="scss" scoped>
$border-radius: 4px;
$color: #ffbedf;
$green: #004935;
.topBarAndBanner {
  background: $color;
  clip-path: ellipse(80% 60% at 50% 40%);
}

.features {
  margin: 64px auto;
  width: 350px;

  @media (min-width: 800px) {
    width: 800px;
  }
  @media (min-width: 1200px) {
    width: 1200px;
  }

  > ul {
    display: flex;
    flex-wrap: wrap;

    > li {
      width: 400px;
      margin: 16px 0;
      display: flex;
      >.wrapper {
        display: grid;
        grid-template-areas:
        "icon title"
        "icon text";
        grid-template-columns: 80px auto;
        grid-template-rows: 1fr auto;

        > svg {
          grid-area: icon;
          width: 64px;
          height: 64px;
        }

        > h3 {
          grid-area: title;
          font-size: 28px;
        }

        > p {
          grid-area: text;
        }
      }
    }
  }
}

.banner {
  padding: 100px 0;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;

  > .actions {
    padding: 8px 0;

    a {
      margin: 0 8px;
      background: $green;
      color: white;
      display: inline-block;
      padding: 8px 24px;
      border-radius: $border-radius;

      &:hover {
        text-decoration: none;
      }
    }
  }
}
</style>