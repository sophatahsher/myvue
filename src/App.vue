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


  ---------------------------------------------------------------------------------------------
  <h2>Conditional List Rendering</h2>
  <template v-for="name in clr" :key="name">    
    <p v-if="name ==='Konitha'" >{{ name }}</p>
  </template>
  ---------------------------------------------------------------------------------------------
  <h2>Learn about Methods</h2>
  <p>{{ add(10,2,3) }}</p>
  <p>Add method: add(10,2,3) - {{ add(10,2,3) }}</p>
  <p>Multiply method: multiply(8) - {{ multiply(8) }}</p>
  ---------------------------------------------------------------------------------------------
  <h2>Learn Event Handling</h2>
  <div class="mt-2 mb-2">    
    <h3>{{varName}}</h3>
    <button v-on:click="changeName($event), increment(1, $event)">Change Me</button>  
  </div>
  <div class="mt-2">
      <label>Count Up/Down</label>
      <h3>{{ count }}</h3>
      <button v-on:click="count +=1">Increment</button>
      <button v-on:click="count -=1">Decrement</button>

      <button v-on:click="increment(1)">Increment(1)</button>
      <button @click="increment(5)">Increment(5)</button>
      <button v-on:click="decrement(1)">Decrement(1)</button>
      <button @click="decrement(5)">Decrement(5)</button>
    </div>
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
      fullNames:[{first:'Brue', last:'Lee'},{first:'Clark', last:'Ken'}, {first:'Princess', last:'Diana'}],
      clr: ['Myura', 'Bosba', 'Konitha', 'Sovvanary'],
      baseMultiplier:5,
      varName:'Sophat',
      count:0
    }
  },
  methods:{
    add(a, b, c){
      return a+b+c;
    },
    multiply(num){
      return num * this.baseMultiplier
    },
    increment(num, event){
      this.count += num
      console.log('Event', event)
    },
    decrement(num){
      return this.count -= num
    },
    changeName(event){
      this.varName = 'Sher'
      console.log('Event', event)
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
.mt-2 {
  margin-top: 15px;
}
.mb-2 {
  margin-bottom: 15px;
}
</style>
