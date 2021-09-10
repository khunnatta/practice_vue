<template>
    <ul v-for="i in myArr">
      <li> {{ i }} </li>
    </ul>

    <h3> Select in object (value, key, index) </h3>
    <ul v-for="(value, key, index) in myObj">
      <li> {{value}}, {{key}}, {{index}} </li>
    </ul>

    <h3> This is data from props </h3>
    <ul v-for="value in testProp">
      <li> {{ value }} </li>
    </ul>
</template>

<script>
export default {
    name: 'Mycomp',
    props: ['testProp'],
    data: function () {
        return {
            myArr: ['dog', 'cat', 'rat'],
            myObj: {
            x: 10,
            y: 20,
            z: 30
            }
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

li {
    margin: 16px;
    display: inline-block;
    color: rgb(228, 153, 153);
}

</style>
