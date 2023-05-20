<template>
  <form class="form" @submit.prevent="handleSubmit">
    <CustomSelect :items="cities" class="form__select" v-model="city" />
    <CustomInput v-model="price" placeholder="Цена, от"/>
    <SubmitButton type="submit" class="form__submit">Подбор жилья</SubmitButton>
  </form>
</template>

<script>
import CustomSelect from "../shared/CustomSelect.vue";
import CustomInput from "../shared/CustomInput.vue";
import SubmitButton from "../CustomButton.vue";
export default {
  name: "ApartmentFilterForm",
  components: {
    CustomInput,
    CustomSelect,
    SubmitButton,
  },
  data() {
    return {
      price: "",
      city: "",
    };
  },
  methods: {
    handleSubmit() {
      this.$emit("submit", {city: this.city, price: this.price});
    },
  },
  computed: {
    cities() {
      return [ {value: '', label: 'Город', selected:true}, "Kyiv", "Odesa", "Kharkiv"];
    },
  },
};
</script>

<style lang="scss" scoped>
.form {
  display: flex;
  align-items: center;
  margin-bottom: 50px;
  &__select {
    margin-right: 30px;
  }
  &__submit {
    margin-left: auto;
  }
}
</style>
