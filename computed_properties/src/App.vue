<template>
  
  <h2>My name is {{fullName}}</h2>
  <p> La moyenne des notes donne {{moyenne}} </p>
  <button @click="notes.push(10)">Add 10 to notes</button>
 
</template>

<script>

export default {
  data(){
    return{
      lastName: "Dolched",
      firstName: "Gabanane",
      notes : [12,14,5,2,10,15,4,7.5,14,18,19,15,20,0,3,5,5],
    }
  },
  methods:{},
  computed: {
    fullName(){
      return `${this.lastName} ${this.firstName}`
    },
    moyenne(){
      var moy=0;
      for(var i in this.notes){
        moy+=this.notes[i]
      }
      return moy/this.notes.length;
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
