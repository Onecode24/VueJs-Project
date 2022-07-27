<template>
  <h2>Music Volume(0-20)</h2>
  <input type="range" v-model="volume" min="0" max="20" />
  <p>{{volume}}</p>
</template>

<script>

export default {
  data(){
    return{
      volume : 0
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
