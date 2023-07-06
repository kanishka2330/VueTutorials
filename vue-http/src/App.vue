<template>
  <div>
    <post-list />
    <template-refs />
    <click-counter/>
    <hover-counter/>
  </div>
</template>

<script>
import postList from "./components/postList.vue";
import templateRefs from "./components/templateRefs.vue";
import clickCounter from "./components/clickCounter.vue";
import hoverCounter from "./components/hoverCounter.vue";

export default {
  name: "App",
  components: {
    postList,
    templateRefs,
    clickCounter,
    hoverCounter
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
