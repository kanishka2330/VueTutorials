<template>
  <div>
    <h2>Options - {{ o_firstName }} {{ o_lasttName }} {{ o_heroName }} </h2>
    <h2>Composition - {{ c_firstName }}</h2>
    <h3>{{greet}} {{greetHero}} </h3>
    <hr>
    <h2>Composition with reactive object:{{state.firstname}} {{state.lastName}}  {{state.heroName}}</h2>
    <h2>Composition w/o using value: {{reactiveGreetHero}}</h2>
  </div>
</template>

<script>
import { ref, reactive } from "vue";
export default {
  name: "DataComponent",
    setup() {
    const c_firstName = ref("Clark");
    const c_lastName = ref("Kent");
    const c_heroName = ref("Superman");

    const greet = `Hello ${c_firstName.value}`
    const greetHero = `Hello ${c_firstName.value} ${c_lastName.value} a.k.a ${c_heroName.value}`

    const state = reactive({
        firstname: 'Princess',
        lastName: 'Diana',
        heroName: 'Wonder Woman'
    })

    const reactiveGreetHero = `Hello ${state.firstname} ${state.lastName} a.k.a ${state.heroName}`

    return {
      c_firstName,
      greet,
      greetHero,
      state,
      reactiveGreetHero
    };
  },
  data() {
    return {
      o_firstName: "Bruce",
      o_lastName: "Wayne",
      o_heroName: "Batman"
    };
  },
};
</script>

<style lang="scss" scoped>
</style>