<template>
  <select v-on="listeners" class="custom-select">
    <option v-for="item in formatedItems" :value="item.value" :key="item.value" :selected="item.selected">
    {{ item.label }}
  </option>
</select>
 
</template>

<script>
export default {
  name: "CustomSelect",
  props: {
    items: {
      type: Array,
      required: true,
    },
  },
  computed: {
    listeners() {
      return {
        ...this.$listeners,
        input: (event) => this.$emit("input", event.target.value),
      };
    },
    formatedItems() {
      return this.items.map((item) => {
        return typeof item === "object" ? item : { value: item, label: item };
      });
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../../assets/scss/variables.scss";
.custom-select {
  max-width: 150px;
  width: 100%;
  height: 40px;
  border: 2px solid $main-color;
  font-size: 18px;
  outline: none;
  line-height: inherit;
  cursor: pointer;
  padding: 8px 15px;
  display: inline-block;
}
</style>
