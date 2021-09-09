<template>
  <div class="hello">
    <h1>{{ msg }}</h1>

    <h2> {{ subTitle }} : {{ age }} </h2>
    <h2 v-if="age>30?true:false"> You are old </h2>

    <button @click="addAge"> add age </button>
    <button v-on:click="resetAge"> resetAge </button> <br>

    <h3> Use function : <input @keyup="readAge"/> </h3>
    <h3> Use V-model : <input v-model="age"/> </h3>
    <h3> Use V-bind & V-on <input v-on:keyup="readAge" v-bind:value="age"> </h3>

    <h3> use Form: 
    <form @submit="addAge">
      <input type="submit">
    </form>
    </h3>

    <h3> Test v-for in array </h3>

    <ul v-for="i in myArr">
      <li> {{ i }} </li>
    </ul>

    <h3> Select in object (value, key, index) </h3>
    <ul v-for="(value, key, index) in myObj">
      <li> {{value}}, {{key}}, {{index}} </li>
    </ul>


    

    <!-- <img :src="myImg" alt=""> -->





  </div>
</template>

<script>
export default {
  name: 'HelloWorld',

  data () {
    return {
    msg: "Hello World",
    subTitle: "age",
    age: 25,
    myImg: 'https://pbs.twimg.com/profile_images/378800000822867536/3f5a00acf72df93528b6bb7cd0a4fd0c.jpeg',
    myArr: ['cat', 'dog', 'rat', 'bat'],
    myObj: {
      x: 10,
      y: 20,
      z: 20
    }
    }
  },
  
  methods: {
    addAge: function() {
      this.age++;
    },
    resetAge: function() {
      this.age = 25;
    },
    readAge: function(input) {
      input.preventDefault();
      this.age = input.target.value;
    }
  },

  props: {
    prop: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

button{
  margin: 10px;
}

img{
  margin: 10px 0 0 0;
}
</style>
