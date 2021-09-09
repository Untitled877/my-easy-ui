<template>
  <div class="easy-attr">
    <h2>Attributes</h2>
    <table class="attr-table">
      <thead>
      <tr>
        <th class="easy-attr-title"
            v-for="(item, index) in columns"
            :key=index>{{ item.title }}
        </th>
      </tr>
      </thead>
      <tbody>
      <tr v-for="item in data">
        <td class="easy-attr-td"
            v-for="(value, index) in item"
            :key=index>
          {{ value }}
        </td>
      </tr>
      </tbody>
    </table>
  </div>
</template>

<script lang="ts">
export default {
  props: {
    columns: {
      type: Object
    },
    data: {
      type: Object
    }
  }
};
</script>

<style lang="scss" scoped>
.easy-attr {
  width: 100%;
  overflow-x: auto;

  h2 {
    font-weight: 400;
    color: #1f2f3d;
    font-size: 22px;
    margin: 55px 0 20px;
  }

  .attr-table {
    width: 100%;
    border-collapse: collapse;
    background-color: #fff;
    font-size: 14px;
    margin-bottom: 45px;
    line-height: 1.5em;
  }

  .easy-attr-title {
    text-align: left;
    white-space: nowrap;
    color: #909399;
    font-weight: 400;
    border-bottom: 1px solid #004935;
    padding: 15px;
    max-width: 250px;
  }

  .easy-attr-td {
    color: #606266;
    white-space: nowrap;
    font-size: 14px;
    border-bottom: 1px solid #dcdfe6;
    padding: 15px;
  }
}
</style>