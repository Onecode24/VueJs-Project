<template>
  <h2>Music Volume(0-20)</h2>
  <input type="range" v-model="volume" min="0" max="20" />
  <p>{{volume}}</p>
  <div>
    <label for="movie">Movie name</label>
    <input type="text" name="movie" id="mobie" v-model="movie">
  </div>
  <div>
    <label for="movie">Movie title</label>
   <input type="text" name="title" id="title" v-model="movieInfos.title">
  </div>
  <div>
    <label for="movie">Principal Actor</label>
    <input type="text" name="actor" id="actor" v-model="movieInfos.actor">
  </div>
  <div>
    <button @click="movieList=movieList.concat(['Wonder Woman'])">add movie</button>
  </div>
  
  
</template>

<script>

export default {
  data(){
    return{
      volume : 0,
      movie: 'Nil',
      movieInfos:{
        title:'',
        actor:'',
      },
      movieList: ['Batman','Superman']
    }
  },
  methods: {
    view() {
      console.log(this.volume);
    }
  },
  watch: {
    volume(newValue,oldValue) {
      if(newValue == 15 && newValue>oldValue) {
       alert('volume is high');
      }
    },
    movie:{
      handler(newValue){
        console.log("search movie named "+ newValue);
      },
      immediate: true
    },
    movieInfos:{
      handler(newValue){
        console.log("Search title: "+newValue.title+" with actor "+newValue.actor);
      },
      deep: true
    },
    movieList:{
      handler(newValue){
        console.log("Movie "+newValue+" is added to list");
      }
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
