<template>
  <h2>js_methods for JavaScript in vue</h2>
  <h3>45+14+5 = {{addNumber(45,14,5)}}</h3>
  <p v-for="name in names" :key="name">{{name}}</p>
  <button @click="ramdonNumber">Clicked</button>
  <p @dblclick="name += 'o'">double cliked me: {{name}}</p>
  <h3>{{count}}</h3>
  <button v-on:click="increment(1)">Increment 1</button><br>
  <button v-on:click="increment(5)">Increment 5</button><br>
  <button @click="decrement(1)">Décrement 1</button><br>
  <button @click="decrement(5)">Decrement 5</button><br>

  <p>{{title}}</p>
  <button @click="changeName($event), increment(2,$event)">Change Name</button>
</template>

<script>


export default {
  data(){
    return {
      names: ['Salon','Sillone','Salimatou','Romain','Danois','Zozoni','Demoniaon'],
      name: 'Angelo',
      count: 0,
      title: 'SOUS TITRE'
    }
  },
  methods: {
    addNumber(a,b,c){
      return a+b+c;
    },
    changeName(){
      this.title= 'HIGH TITLE'
    },
    ramdonNumber(){
      this.names = this.names.sort(()=>Math.random()-0.5);
    },
    increment(a){
      this.count+=a;
    },
    decrement(a){
      this.count-=a;
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
</style>
