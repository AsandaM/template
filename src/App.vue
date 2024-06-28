<template>
  <navBarComp/>
  <router-view/>
  <footer-comp/>
</template>

<script>
import NavBarComp from "./components/NavbarComp.vue";
import FooterComp from "./components/FooterComp.vue";
export default{
  components:{
    NavBarComp,
    FooterComp
  }
}
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
body {
    font-family: Arial, sans-serif;
    margin: 0; /* Remove default margin */
    background: linear-gradient(to right, #F5F5F5 0%, #f5f5f5 50%, #C9CC3F 50%, #C9CC3F 100%);
    
}

nav a.router-link-exact-active {
  border-bottom: 2px solid #aa7b4c; /* Highlight the active link */
}
nav a:hover {
  color:  #007bff;
}

.navbar {
  background-color: #FFF8F3;
  display: flex;
  justify-content: space-between;
  color: #0f0e0d;  
  padding: 1rem 2rem;
}

.menu {
  display: flex;
}

.menu a {
  text-decoration: none;
  margin: 0 1rem;
  color: #100f0f;
  position: relative;
  display: block;
  z-index: 999;
  font-size: 20px;
  margin-top: 20% ;
}

.outter::before,
.outter::after,
.inner::before,
.inner::after {
  content: "";
  position: absolute;
  background: #080808;
  transition: transform 0.6s ease;
}

.outter::before,
.outter::after {
  height: 1px;
  width: calc(100% + 12px);
  top: 0;
  left: -8px;
  transform: scale(0);
}

.outter::after {
  bottom: 0;
  transform-origin: right;
}

.inner::before,
.inner::after {
  width: 1px;
  height: calc(100% + 10px);
  top: -5px;
  transform: scale(0);
}

.inner::before {
  left: -2px;
  transform-origin: bottom;
}

.inner::after {
  right: 0;
  transform-origin: top;
}

.menu a:hover .outter::before,
.menu a:hover .outter::after,
.menu a:hover .inner::before,
.menu a:hover .inner::after {
  transform: scale(1);
}
</style>
