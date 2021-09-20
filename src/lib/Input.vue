<template>
  <div class="easy-input-wrapper">
    <input class="easy-input"
           :class="{'easy-input-error':errorMsg}"
           :type="type"
           :placeholder="placeholder"
           :disabled="disabled"
           :value="value"
           :errorMsg="errorMsg"
           @input="handleInput"/>
    <span v-if="errorMsg" class="easy-input-errorMsg">{{errorMsg}}</span>
  </div>
</template>

<script lang="ts">

export default {
  props: {
    placeholder: {
      type: String,
      default: '',
    },
    type: {
      type: String,
      default: 'text',
    },
    disabled: {
      type: Boolean,
      default: false
    },
    value: {
      type: String,
      default: ''
    },
    errorMsg: {
      type: String
    }
  },
  setup(props, context) {
    const handleInput = (e) => {
      context.emit('update:value', e.target.value);
    };
    return {handleInput};
  }
};
</script>

<style lang="scss">
$green: #004935;
.easy-input-wrapper {
  font-size: 14px;
  display: inline-block;
  .easy-input {
    border: 1px solid #ddd;
    line-height: 22px;
    padding: 4px 8px;
    border-radius: 4px;
    box-shadow: 0 0 0 2px fade_out($green, 1);
    transition: box-shadow 250ms;
    width: 100%;
    &:focus {
      outline: none;
      border-color: $green;
      box-shadow: 0 0 0 2px fade_out($green, 0.5);
    }
    &:hover{
      border-color: $green;
    }
    &[disabled] {
      border-color: #e4e7ed;
      color: #c0c4cc;
      cursor: not-allowed;
    }
  }
  .easy-input-error {
    border-color: #cf222e;
    &:hover {
      border-color: #cf222e;
      box-shadow: 0 0 0 2px fade_out(#cf222e, 0.5);
    }
  }
  .easy-input-errorMsg {
    color: #cf222e;
    margin-left: 5px;
  }
}

</style>