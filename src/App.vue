<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <h2>Upload file exel to send email</h2>
  <FormUpload/>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import FormUpload from './components/FormUpload.vue';
// import HelloWorld from './components/HelloWorld.vue';

export default defineComponent({
  name: 'App',
  components: {
    FormUpload
}
});
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
