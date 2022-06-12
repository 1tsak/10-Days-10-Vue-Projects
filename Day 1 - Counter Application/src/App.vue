<template>
  <div class="main">
    <h1>Day 1- Counter App</h1>
    <div class="card">
      <!-- Event Binding:- In vue you can bind any event to any method by adding the v-on directive to the event like in this case v-on:click for click event, you can also use the shorthand @ introduced in recent versions of vue. the short hand of click event will be @click -->
      <button v-on:click="increment()" class="btn-action">Increment +</button>
      <button v-on:click="decrement()" class="btn-action">Decrement -</button>
      <!-- Interpolation:- If you want to output the value of your data defined in your data object you can do it simply by using the interpolation sign which is {{}} (Double Close Curly-braces) -->
      <p>Count is: {{ count }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
  // Data:- If you want to define any variables or data which you want to use in your app you can do it by wrapping them inside data as i have done below, data itself is a function which returns an object which you can use to define key pair values.
  data() {
    return {
     // its like state once a data is updated the associated component will be re-rendered on the screen again, that means each time the count will be updated the associated paragraph will be rendered again.
      count: 0,
    };
  },
  // Methods:- If you want to define functions you can do it by wrapping up inside the methods object.
  methods: {
    // You can define like key pair values.
   increment:function  () {
      this.count++;
    },
    // Or you can use method shorthand like this.
    decrement() {
      this.count--;
    },
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
.main {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.btn-action {
  padding: 8px 16px;
  color: white;
  margin: 10px;
  background-color: rgb(246, 37, 37);
  border-radius: 10px;
  border: none;
  cursor: pointer;
}
.card {
  padding: 15px 25px;
  border-radius: 5px;
  box-shadow: 0px 0px 5px 3px rgba(0, 0, 0, 0.2);
}
</style>
