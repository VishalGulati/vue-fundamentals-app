<template>
  <div class="home">
    <div class="sample">
      <p class="sample-title">Interpolation</p>
      <h2>{{msg}}</h2>
    </div>
    <div class="sample">
      <p class="sample-title">v-bind & its shortcut</p>
      <img class="logo" v-bind:src="logo" />
      <img class="logo" :src="logo" />
    </div>
    <div class="sample">
      <p class="sample-title">v-on & its shortcut</p>
      <p>{{clickCounter}}</p>
      <button v-on:click="clickCounter++">Increment counter!</button>
      <button @click="clickCounter++">Increment counter!</button>
    </div>
    <div class="sample">
      <p class="sample-title">Computed properties</p>
      <p>{{formattedAmount}}</p>
    </div>
    <div class="sample">
      <p class="sample-title">v-html</p>
      <p v-html="dynamicHtml"></p>
    </div>
    <div class="sample">
      <p class="sample-title">v-if & v-else</p>
      <p v-if="seen">Now you see me</p>
      <p v-else>Now you dont</p>
      <button @click="seen=!seen">Click to toggle!</button>
    </div>
    <div class="sample">
      <p class="sample-title">class binding</p>
      <span :class="{orangeText : seen }">Toggles with v-if</span>
    </div>
    <div class="sample">
      <p class="sample-title">v-show</p>
      <p v-show="seen">Now you see me</p>
      <button @click="seen=!seen">Click to toggle!</button>
    </div>
    <div class="sample">
      <p class="sample-title">v-for</p>
      <ol class="listOl">
        <li v-for="(todo, index) in todos" :key="index">{{ todo }}</li>
      </ol>
    </div>
    <div class="sample">
      <p class="sample-title">v-model and methods</p>
      <input v-model="newTodo" />
      <button @click="addTodo" :disabled="!newTodo">Add new to-do!</button>
    </div>
    <div class="sample">
      <p class="sample-title">Rendering child component with props</p>
      <nested-component parent="HomePage" />
    </div>
  </div>
</template>

<script>
import NestedComponent from "./components/NestedComponent";
export default {
  // Name of the component
  name: "HomePage",
  // child components referenced in this component
  components: {
    NestedComponent
  },
  // local state of the component
  data: function() {
    return {
      msg: "Hello Vue!",
      seen: true,
      todos: ["New Task", "VueJS session"],
      logo: "https://vuejs.org/images/logo.png",
      clickCounter: 0,
      amount: 1099,
      dynamicHtml: "<span class='orangeText'>Just like innerHTML!</span>",
      newTodo: ""
    };
  },
  // derived/modified properties that are cached
  computed: {
    formattedAmount() {
      return (
        "INR " + this.amount.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ",")
      );
    }
  },
  // functions called inside template
  methods: {
    addTodo() {
      this.todos.push(this.newTodo);
      this.newTodo = "";
    }
  },
  // lifecycle hooks of the component
  created() {
    console.log("inside HomePage");
  }
};
</script>

<style>
.home {
  text-align: center;
  padding: 20px;
}
.sample {
  min-height: 200px;
  border: 2px solid black;
  border-radius: 5px;
  margin-bottom: 10px;
}
.sample-title {
  text-align: left;
  padding: 10px;
}
button {
  background-color: burlywood;
  margin: 10px;
  padding: 5px;
  border: 1px solid black;
  border-radius: 2px;
  opacity: 1;
}
button:disabled {
  opacity: 0.5;
}
.listOl li {
  margin: 0 50px;
}
.logo {
  height: 50px;
  width: 50px;
  display: block;
  margin: 10px auto;
}
.orangeText {
  color: orangered;
}
input {
  border: 2px solid black;
}
</style>
