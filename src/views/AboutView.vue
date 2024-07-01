<template>
  <div class="about">
    <div class="container text-center mt-5">
    <h1 class="mb-4">ABOUT ME</h1>
    <p class="lead mb-4">
      I'm <strong>Asanda Mehlo</strong>, Full Stack Developer.
    </p>
    <p class="mb-4">
      <about-comp :about-data="about"></about-comp>
    </p>
    <div class="row text-center mb-5">
      <h2>Professional Certificates</h2>
      <div class="col-md-6 mb-4">
        <div class="stats-box p-3">
          <h2>AWS</h2> 
          <p>link to download</p>
        </div>
      </div>
      <div class="col-md-6 mb-4">
        <div class="stats-box p-3">
          <h2></h2>
          <p></p>
        </div>
      </div>
      <div class="col-md-6 mb-4">
        <div class="stats-box p-3">
          <h2></h2>
          <p></p>
        </div>
      </div>
      <div class="col-md-6 mb-4">
        <div class="stats-box p-3">
          <h2></h2>
          <p></p>
        </div>
      </div>
    </div>
    <div class="row text-left">
      <div class="col-md-4 offset-md-4">
        <h3 class="mb-4">TECHNICAL SKILLS</h3>
        <ul class="list-unstyled">
          <li v-for="(skills, category) in technicalSkills" :key="category" class="mb-3">
              <h5>{{ category }}</h5>
              <p>{{ skills.join(', ') }}</p>
            </li>
        </ul>
      </div>
    </div>
  </div>
  </div>
</template>

<script>
import AboutComp from '../components/AboutComp.vue'
export default {
  components: {
    AboutComp
  },
  computed: {
    about() {
      // Assuming this.$store.state.aboutMe is an object with a text property
      return this.$store.state.aboutMe;
    },
    technicalSkills(){
      return this.$store.state.technical_skills;
    }
  },
  mounted() {
    this.$store.dispatch('getData');
  }
}
</script>

<style scoped>
body {
  background-color: #f5f5f5;
  font-family: Arial, sans-serif;
}

h1 {
  font-size: 3rem;
  font-weight: bold;
  text-transform: uppercase;
}

.lead {
  font-size: 1.25rem;
}

.stats-box {
  background-color: #333;
  color: #fff;
  border-radius: 5px;
}

.stats-box h2 {
  font-size: 2.5rem;
  font-weight: bold;
}

.stats-box p {
  margin: 0;
}

h3 {
  font-size: 1.75rem;
  font-weight: bold;
}

ul li h5 {
  font-size: 1.25rem;
  font-weight: bold;
}

ul li p {
  margin: 0;
}

.about{
  background-color: rgba(145, 186, 159, 0.6);
  
}

</style>
