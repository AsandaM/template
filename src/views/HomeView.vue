<template>
  <!-- <div class="home">
    <img alt="Vue logo" src="https://asandam.github.io/images/asaM.jpg">
    <HelloWorld msg="Welcome to My Portfolio"/>
  </div> -->

  <div class="container text-center">
  <div class="row">
    <div class="col align-self-start ring-container">
      <div class="ring">
        <i style="--clr:#00ff0a;"></i>
        <i style="--clr:#ff0057;"></i>
        <i style="--clr:#fffd44;"></i>
        <div class="image">
          <img src="https://asandam.github.io/images/asaM.jpg" alt="Your Name" class="img-fluid rounded-circle" style="max-width: 350px;"> 
        </div>

      </div>
    </div>
    <div id="back" class="col align-self-center">
      <HelloWorld msg="Welcome to My Portfolio"/>
    </div>
  </div>
</div>

</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'HomeView',
  components: {
    HelloWorld
  }
}
</script>

<style scoped>

.ring-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100%;
}

.ring {
  position: relative;
  width: 500px;
  height: 500px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.ring i {
  position: absolute;
  inset: 0;
  border: 1px solid #C9CC3F;
  transition: 0.5s;
}

.ring i:nth-child(1) {
  border-radius: 38% 62% 63% 37% / 41% 44% 56% 59%;
  animation: animate 6s linear infinite;
}

.ring i:nth-child(2) {
  border-radius: 41% 44% 56% 59%/38% 62% 63% 37%;
  animation: animate 4s linear infinite;
}

.ring i:nth-child(3) {
  border-radius: 41% 44% 56% 59%/38% 62% 63% 37%;
  animation: animate2 10s linear infinite;
}

.ring:hover i {
  border: 6px solid var(--clr);
  filter: drop-shadow(0 0 20px var(--clr));
}

@keyframes animate {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}

@keyframes animate2 {
  0% {
    transform: rotate(360deg);
  }
  100% {
    transform: rotate(0deg);
  }
}

#back{
  background-color: rgba(201, 232, 160, 0.6);
  /* height: calc(100vh - 300px); */
}

</style>
