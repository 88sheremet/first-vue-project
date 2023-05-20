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
@import '../assets/scss/variables.scss';
button {
  max-width: 150px;
  width: 100%;
  background-color: $main-color;
  color: #fff;
  height: 40px;
  outline: none;
  border:none;
  cursor: pointer;
}
</style>
