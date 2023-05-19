<template>
  <button :type="type">
    <slot></slot>
  </button>
</template>

<script>

export default {
  name: "CustomButton",
  props: {
    type:{
      type: String,
      default: 'button'
    },
    outlined:{
      type: Boolean,
      default: false
    }
  }
};
</script>

<style lang="scss" scoped>

button {
  width: 150px;
  background-color: black;
  color: gold;
  height: 40px;
}
</style>
