<template>
  <div class="app">
    <!-- <h2>{{ text }}</h2> -->
   <Container> 
    <ApartmentFilterForm class="apartments-filter" @submit="logger"/>
  </Container>
   
    
    <ApartmentList :items="apartments" />
  </div>
</template>

<script>
import ApartmentList from "./components/apartment/ApartmentsList.vue";
import apartments from "./components/apartment/apartments";
import Container from "./components/shared/Container.vue";
import ApartmentFilterForm from "./components/apartment/ApartmentFilterForm.vue";
export default {
  name: "App",

  components: {
    ApartmentList,
    ApartmentFilterForm,
    Container,
    // CustomSelect
  },

  data() {
    return {
      apartments,
      text:'',
    };
  },
  methods: {
    logger(value){
      console.log(value, '----form value')
    }
  },
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
  margin-top: 60px;
}
.apartments-filter{
margin-bottom: 40px;
}
</style>
