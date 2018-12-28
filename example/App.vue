<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <VFormDialog v-model="dialogVisible" msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import VFormDialog from "@/components/VFormDialog.vue";

export default {
  name: "app",
  data() {
    return {
      dialogVisible: true
    };
  },
  components: {
    VFormDialog
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
