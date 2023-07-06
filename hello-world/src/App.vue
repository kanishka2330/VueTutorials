<template>
  <div :id="heading">
    Hello there {{ name }}!
    <h1 v-html="link"></h1>
    <h2 :class="'myMessage'">Here {{ message }}</h2>
    <div :class="ticketAvailability? 'availableColor': 'notAvailableColor'">Tickets</div>
    <div :class="theatreAvailability? 'availableColor': 'notAvailableColor'">Theatres</div>
    <div :style="{
      color: 'pink',
      fontSize: headerSize + 'px',
      padding: '20px'
    }">Click the button below to book tickets</div>

    <br />
    <button id="submitBtn" :class="{'disabled': !ticketAvailability || !theatreAvailability}" @click="showAlert">Click Me</button>

    <div v-for="color in colorObject" :key="color.first">
      <h2>{{color.first}} {{color.last}}</h2>
      <template v-for="surnames in color.last" :key="surnames">
        <h4 v-if="surnames==='Mehta'">{{surnames}}</h4>
      </template>
    </div>
    <h1>My age is {{add(5, 2, 6)}}</h1>
    <h4>{{count}}</h4>
    <button v-on:click="increment(1, $event), changeName($event)">Increment 1</button>
    <button v-on:click="decrement(2, $event)">Decrement 2</button>

  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      count: 0,
      message: "Book your tickets now!",
      heading: "title",
      name: "Kanishka",
      link: `<a href="#" onclick="alert('you have been hacked!')"> Win a prize! </a> `,
      ticketAvailability: false,
      theatreAvailability: true,
      headerSize: 50,
      colorObject : [{first: 'Kanishka', last: ['Malviya', 'Mehta', 'Patel']}, {first: 'Tashi', last: ['Malviya', 'Patel', 'Mehta']}]
    };
  },
  methods: {
    add(a, b, c){
      return a+b+c;
    },
    showAlert() {
      alert('Yayy tickets booked!');
    },
    increment(num, event){
      this.count+=num;
      console.log('event', event);
    },
    decrement(num, event){
      this.count-=num;
      console.log('event', event);
    },
    changeName(){
      this.name= "Bhature";
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

.myMessage {
  text-decoration: underline;
}

.notAvailableColor {
  color: red;
}

.availableColor {
  color: green;
}

.disabled {
  opacity: 0.6;
  cursor: not-allowed;
}
</style>
