<template>
  <div id="rootNode">
    <greet-component
      id="ideal"
      class="great"
      hero="Romeo"
      heroine="Juliet"
      age="35"
    ></greet-component>
    <greet-component
      :hero="myhero"
      :heroine="myheroine"
      :age="age"
    ></greet-component>
    <component-a />
    <div>I provide this {{username}}</div>
    <hr>
    <input-custom-component v-model="myName"/>
    <hr>
    <button @click="showPopup = true">Show Pop Up</button>
    <pop-up v-show="showPopup" @close="closePopup"></pop-up>
    <hr>
  </div>
</template>

<script>
import ComponentA from "./components/componentA.vue";
import GreetComponent from "./components/Greet.vue";
import popUp from "./components/pop-up.vue";
import InputCustomComponent from "./components/input.vue"


export default {
  name: "App",
  components: {
    GreetComponent,
    ComponentA,
    popUp,
    InputCustomComponent
  },
  data() {
    return {
      username: "Kanishka",
      myhero: "Jodha",
      myheroine: "Akbar",
      age: 42,
      showPopup: false,
      myName: '',
    };
  },
  provide() {
    return {
    name: this.username,
    }
  },
  methods: {
    closePopup(name){
      this.showPopup = false;
      console.log('name', name);
    }
  }
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
