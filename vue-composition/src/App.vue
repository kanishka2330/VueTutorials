<template>
  <div>
    <data-component/>
    <hr>
    <demo-1></demo-1>
    <hr>
    <demo-2></demo-2>
    <methods-component></methods-component>
    <v-model-component/>
    <hr>
    <computed-component/>
    <hr>
    <watch-component/>
    <provide-inject/>
    <person-component/>
  </div>
</template>

<script>
import DataComponent from './components/Data.vue'
import Demo1 from './components/Demo1.vue'
import Demo2 from './components/Demo2.vue'
import methodsComponent from './components/methods.vue'
import vModelComponent from './components/vModel.vue'
import computedComponent from './components/computed.vue'
import watchComponent from './components/watch.vue'
import provideInject from './components/provideInject.vue'
import personComponent from './components/person.vue'

export default {
  name: 'App',
  components: {
    DataComponent,
    Demo1,
    Demo2,
    methodsComponent,
    vModelComponent,
    computedComponent,
    watchComponent,
    provideInject,
    personComponent
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
