<template>
  <div id="app1" class="container mt-5">
   <font-awesome-icon icon="shopping-cart"></font-awesome-icon>
   <h1>shopping cart </h1>
 
    <HelloWorld msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import {FontAwesomeIcon} from '@fortawesome/vue-fontawesome';

export default {
  name: "App",
  components: {
    HelloWorld,
    FontAwesomeIcon
  },
};
</script>

<style>
#app1 {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
