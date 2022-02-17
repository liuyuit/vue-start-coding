<template>
  <div id="app">
    <img src="./assets/logo.png">
    <h1>{{ msg }}</h1>
    <firstcomponent></firstcomponent>
    <secondcomponent></secondcomponent>
    <div id="app-in">
      <h1>{{ msg }} Here</h1>
    </div>
  </div>
</template>

<script>
import firstcomponent from './component/firstcomponent.vue';
import secondcomponent from './component/secondcomponent.vue';

export default {
  data() {
    return {
      msg: "Hello Vue!"
    };
  },
  components: {firstcomponent, secondcomponent}
}
</script>
<style>
body {
  font-family: Helvetica, sans-serif;
}
</style>

