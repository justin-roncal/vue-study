<template>
  <div class="test">
    <input type="text" v-model="title">
    <br>
    <h1>{{title}}</h1>
    <p v-if="showName">{{user.first_name}}</p>
    <p v-else="showName">nobody</p>

    <ul>
      <li v-for="item in items">{{item.title}}</li>
    </ul>
    <button v-on:click="greet('Hello World')">Say Greeting</button>
    <br>
    <input type="text" v-on:keyup="pressKey" v-on:keyup.enter="onEnterHit">
    <hr>
    <label>First Name:</label>
    <input type="text" v-model="user.first_name">
    <br>
    <label>Last Name:</label>
    <input type="text" v-model="user.last_name">
    <br>
    <h3>{{fullname}}</h3>
    <h2>{{msg}}</h2>
  </div>
</template>

<script>
export default {
  name: "test",
  props: {
    msg: {
      type: String,
      default: "Foobar"
    }
  },
  data() {
    return {
      title: "",
      user: {
        first_name: "John",
        last_name: "Doe"
      },
      showName: false,
      items: [{ title: "Item 1" }, { title: "Item 2" }, { title: "Item 3" }]
    };
  },
  methods: {
    greet: function(greeting) {
      alert(greeting);
    },
    pressKey: function(e) {
      console.log(e.target.value);
    },
    onEnterHit: function() {
      console.log("You hit enter");
    }
  },
  computed: {
    fullname: function() {
      return this.user.first_name + " " + this.user.last_name;
    }
  }
};
</script>

<style scoped>
</style>

