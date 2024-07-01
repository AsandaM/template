<template>
    <div>
      <testimonials-comp :items="testimonials" />
    </div>
  </template>
  
  <script>
  import TestimonialsComp from '../components/TestimonialsComp.vue';
  
  export default {
    components: {
      TestimonialsComp
    },
    computed: {
    testimonials() {
      // Assuming this.$store.state.aboutMe is an object with a text property
      return this.$store.state.testimonials;
    }
  },
  mounted() {
    this.$store.dispatch('getData');
  }
  };
  </script>
  
  <style>
 
  </style>
  