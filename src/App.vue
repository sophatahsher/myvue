<template>
  <div> {{ name }}</div>
  <h2 v-if="num===0"> The number is zero</h2>
  <h2 v-else-if="num<0"> The number is negative</h2>
  <h2 v-else-if="num > 0"> The number is positive</h2>
  <h2 v-else> Not a Number</h2>

  <template v-if="display">
    <h2>Sher</h2>
    <h2>CodeVueJs</h2>
    <h2>Vue</h2>
  </template>

  <h2 v-for="color in arrays" :key="color">{{ color }}</h2>
  <h2 v-for="name in fullNames" :key="name.first">{{ name.first }} {{ name.last }}</h2>

</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      name:"Hello World",
      num:-3,
      display: true,
      arrays:['Red', 'Orange', 'Blue'],
      fullNames:[{first:'Brue', last:'Lee'},{first:'Clark', last:'Ken'}, {first:'Princess', last:'Diana'}]
    }
  }
}
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

element.style{
  display: none;
}
</style>
