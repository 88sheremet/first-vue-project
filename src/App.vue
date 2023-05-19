<template>
  <div class="app">
    <h2>{{ text }}</h2>
   
    <CustomInput v-model="text"/>
    <ApartmentList :items="apartments" />
  </div>
</template>

<script>
import ApartmentList from "./components/apartment/ApartmentsList.vue";
import apartments from "./components/apartment/apartments";
import CustomInput from './components/shared/CustomInput.vue'

export default {
  name: "App",

  components: {
    ApartmentList,
    CustomInput,
  },

  data() {
    return {
      apartments,
      text:'',
    };
  },
  methods: {},
};
</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app {
  font-family: Montserrat, sans-serif;
  padding: 20px;
}
</style>
