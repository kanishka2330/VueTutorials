<template>
  <div>
    <hr>
    <div>
    Fullname: {{ firstName }} {{ lastName }}
    </div>
    <br>
    <div>
      <button @click="changeFullName">Change Name and set it to computed property and data property </button>
    </div>
    <h2>Computed {{ fullName }}</h2>
    <hr>
    <h1>Computed {{ totals }}</h1>
    <div>
      <button @click="items.push({ id: 4, title: 'heater', price: 350 })">
        Add item to get newly computed property
      </button>
      <hr>
    </div>
    <h3 v-for="item in expensive" :key="item.id">
      Computed {{ item.title }} {{ item.price }}
    </h3>
    <hr>
    <h2>{{volume}}</h2>
    <button @click="volume+=2">Increase Volume</button>
    <button @click="volume-=2">Decrease Volume</button>
    <hr>

  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      volume: 0,
      firstName: "Kanishka",
      lastName: "Malviya",
      items: [
        { id: 1, title: "tv", price: 250 },
        { id: 2, title: "fridge", price: 400 },
        { id: 3, title: "ac", price: 500 },
      ],
    };
  },
  methods: {
    changeFullName(){
      this.fullName = 'Ben Stokes'
    }
  },
  computed: {
    fullName: {
      get() {
        return `${this.firstName} ${this.lastName}`;
      },
      set(value) {
        const names = value.split(' ');
        this.firstName = names[0];
        this.lastName = names[1];
      },
    },
    totals() {
      return this.items.reduce((total, curr) => (total += curr.price), 0);
    },
    expensive() {
      return this.items.filter((item) => item.price > 300);
    },
  },
  watch: {
    volume(newValue, oldValue){
      if(newValue===16 && newValue>oldValue){
        alert('High Volume');
      }
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
