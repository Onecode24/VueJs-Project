<template>
  <h3 v-for="(name,index) in names" :key="name" v-bind:class="textColor">{{index}} {{name}}</h3>
  <p v-for="full in fullname" :key="full.first"> My name is {{full.first}} {{full.last}}</p>

  <div v-for="actor in actors" :key="actor.name">
    <h3 :class="nameStyle">{{actor.name}}</h3>
    <p v-for="movie in actor.movies" :key="movie">{{movie}}</p>
  </div> 

  <h4 v-for="(value, key) in objectInfos" :key="value">{{key}} : {{value}}</h4>

  <!--to see difference when we use :key attribute and not use-->

  <template v-for="(name,index) in keyNames" :key="name">
    <p v-if="index===0">This is the first element</p>
    <h4>{{name}} at index {{index}}</h4>
    <input type="text" placeholder="your name"/>
    <hr>

  </template>
  <button @click="shuffle">Shuffle</button>


</template>

<script>

export default{
  data(){
    return{
      names : ['Angelo','Gabrielle','Solange'],
      fullname: [
        {first: 'SALONMON',last: 'Romain'},
        {first: 'PAUL', last: 'Simon'},
        {first: 'DEMONE', last: 'Emeraude'}
      ],
      actors:[
        {
          name:'Angelo',
          movies: ['Underground 8','Fall in street war']
        },
        {
          name:'Serge',
          movies: ['Titanic 22','Back in prison'] 
        }
      ],
      objectInfos : {
        name : 'Solania',
        age : 25,
        sex: 'women'      
      },

      //names for :key attributes test
      keyNames : ['Tony', 'Stark', 'Paul', 'Vincent','Tony'],

      textColor : 'text-color',
      nameStyle: 'actorName'
    };
  },
  methods: {
    shuffle(){
      this.keyNames = this.keyNames.sort(()=> Math.random()-0.5);
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

.text-color{
  color: #2ed402;
}

.actorName{
  color: chocolate;
  text-decoration: dashed;
}
</style>
