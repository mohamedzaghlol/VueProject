<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/>
  <div id="app">
    <CreatePerson />
    <PersonDetails />
    <UpdatePerson />
  </div>

</template>

<script>
import CreatePerson from './components/CreatePerson.vue';
import HelloWorld from './components/HelloWorld.vue'
import PersonDetails from './components/PersonDetails.vue';
import UpdatePerson from './components/UpdatePerson.vue';

export default {
  name: 'App',
  components: {
    HelloWorld,
    CreatePerson,
    PersonDetails,
    UpdatePerson
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
  margin-top: 60px;
}
</style>
