<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>I'm a Full-Stack Developer passionate about creating amazing digital experiences.</p>
      <a href="#about" class="btn btn-primary btn-get-started">More about me</a>
      <a href="#about" class="btn btn-primary btn-get-started">More about me</a>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hello{
  color:black;
}

.hello a{
  margin: 10px;
}
</style>
