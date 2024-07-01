<template>
    <div>
      <p>{{ safeText }}</p>
    </div>
  </template>
  
  <script>
  // In AboutComp.vue's script
export default {
  props: {
    aboutData: {
      type: Object,
      default: () => ({}), // Provide a default empty object
    },
  },
  computed: {
    safeText() {
      return this.aboutData ? this.aboutData.text : 'Loading...';
    },
  },
}
  </script>