<template>
  <button class="bc-Button" :type="type" :class="color">{{ message }}</button>
</template>

<script>
// Simple button component with message, type and color attributes
export default {
  name: 'Button',
  props: {
    message: {
      default: 'New button',
      type: String
    },
    type: {
      default: 'button',
      type: String
    },
    color: {
      default: 'green',
      type: String
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
$bg-default: #018aa2;
$bg-negative: #a72a2a;
$bg-bland: #fff;
$text-default: #fff;
$text-bland: #333;

.bc-Button {
  border-radius: 3px;
  color: $text-default;
  cursor: pointer;
  display: block;
  float: left;
  font-size: 15px;
  line-height: 30px;
  height: 40px;
  text-align: center;
  outline: 0;
  padding: 0 20px;
  width: auto;
  transition: background .2s linear;

  &.green {
    background: $bg-default;

    &:hover {
      background: #006a7c;
    }
  }

  &.white {
    background: $bg-bland;
    color: $text-bland;

    &:hover {
      background: #e5e5e5;
    }
  }

  &.red {
    background: $bg-negative;

    &:hover {
      background: #872222;
    }
  }
}
</style>
