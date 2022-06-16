<template>
  <div class="card">
    <h1>My Goals</h1>
    <!-- V-MODEL:- It binds the data to the component, its two way binding that means if data will be updated component will be rendered again and vice versa -->
    <input v-model="goal" type="text" placeholder="Enter Goals.." />
    <Button @click="addGoal">Add</Button>
    <!-- Conditional Rendering :- You Can Render Components beased on a condition the v-if and v-else are used for this v-if accepts a boolean logic and if the logic will be true then only the associated component will be added to the dom -->
    <p v-if="Goals.length === 0">
      No Goals to show add your first goal to see it here..
    </p>
    <!-- v-if and v-else will work only if the v-if and v-else are adjacent elements. -->
    <ul v-else>
      <!-- v-for:- the v-for directive is used for iterating over a list or an array you can achieve that as shown below -->

      <!-- Event Modifiers:-These are used to modify an event like if u want to stop propagation of event then you can call .stop or you can also add more specification to event as i have done below for right click -->
      <li v-for="goal in Goals" :key="goal" @dblclick.left="removeGoal(goal)">
        <div>
          <p>{{ goal }}</p>
        </div>
      </li>
    </ul>
    <!-- v-show is a bit similar to v-if it is also used for sshowing or hiding elements but unlike v-if which add or remove from dom it only hide and display component with css. -->
    <p v-show="Goals.length!=0">Tip:- Double Click To Remove An Item From List</p>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      Goals: [],
      goal: "",
    };
  },
  methods: {
    addGoal() {
      this.Goals.push(this.goal);
      this.goal = "";
    },
    removeGoal(key) {
      this.Goals.pop(key);
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
.card {
  text-align: center;
  margin: auto;
  padding: 25px;
  max-width: 500px;
  box-shadow: 0 0 1px 1px rgba(0, 0, 0, 0.1);
}
ul {
  list-style: none;
}
li {
  padding: 10px 25px;
  box-shadow: 0 0 1px 1px rgba(0, 0, 0, 0.1);
}
li div {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
button {
  padding: 5px 25px;
  margin: 10px;
  cursor: pointer;
}
input {
  padding: 5px 10px;
}
</style>
