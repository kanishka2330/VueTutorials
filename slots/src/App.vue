<template>
  <div>
    <card-component>Card Content</card-component>
    <card-component><h2>Card Content</h2></card-component>
    <card-component><img src="https://picsum.photos/200" alt="myPhoto"/></card-component>

    <card-component>
      <template v-slot:header>
        <h3>Header</h3>
      </template>
      <template v-slot:default>
        <img src="https://picsum.photos/200" alt="myPhoto" />
      </template>
      <template v-slot:footer>
        <button>View Details</button>
      </template>
    </card-component>
    <h3>Using slots to render content at different pages </h3>
    <name-list>
      <template v-slot:default="slotProps">
        {{slotProps.firstName}} {{slotProps.lastName}}
      </template>
    </name-list>
    <name-list>
      <template v-slot:default="slotProps">
        {{slotProps.lastName}} {{slotProps.firstName}}
      </template>
    </name-list>
    <name-list>
      <template v-slot:default="slotProps">
        {{slotProps.firstName}}
      </template>
    </name-list>
    <hr>
    <h4>App Component Text</h4>
    <child-styles/>
    <hr>
    <button @click="activeTab='TabA'">Tab A</button>
    <button @click="activeTab='TabB'">Tab B</button>
    <button @click="activeTab='TabC'">Tab C</button>

    <keep-alive>
    <component :is="activeTab"></component>
    </keep-alive>
    <!-- <tab-a v-if="activeTab==='A'"></tab-a>
    <tab-b v-if="activeTab==='B'"></tab-b>
    <tab-c v-if="activeTab==='C'"></tab-c> -->
    <hr>
    <teleport to="#portal-root">
    <portal-component/>
    </teleport>
  </div>
</template>

<script>
import CardComponent from "./components/card.vue";
import NameList from "./components/nameList.vue";
import ChildStyles from "./components/ChildStyles.vue";
import TabA from "./components/TabA.vue";
import TabB from "./components/TabB.vue";
import TabC from "./components/TabC.vue";
import portalComponent from "./components/portal.vue";

export default {
  name: "App",
  components: {
    CardComponent,
    NameList,
    ChildStyles,
    TabA,
    TabB,
    TabC,
    portalComponent
  },
  data() {
    return {
      activeTab: "TabA",
    }
  }
};
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  display: flex;
}

h4{
    color: rgb(19, 0, 128)
}
</style>
