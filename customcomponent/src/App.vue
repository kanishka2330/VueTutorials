<template>
  <div>
    <input-component v-model="name"></input-component>
  </div>
</template>

<script>
import inputComponent from "./components/inputComponent.vue";
export default {
  name: "App",
  components: {
    inputComponent,
  },
  data() {
    return {
      name: "",
    };
  },
};
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
