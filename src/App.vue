<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <hello />
</template>

<script>
import hello from './components/hello.vue';
export default {
    name: 'App',
    data() {
    },
    components: { hello }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
