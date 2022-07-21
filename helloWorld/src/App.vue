<template>
  <div> {{name}} </div>
  <div v-text="source"></div>
  <div v-html="html"></div>
  <h2 v-bind:id="id">Header</h2>
  <button v-bind:disabled="disabled">Button</button>
  <h2 v-bind:style="{
    color: highlight
  }">Binding style in html</h2>
  <h2 v-bind:style='style'>Style Object from data</h2>

  <p v-if="num === 0">v-if for number is zero</p>
  <p v-else-if="num < 0">v-else-if for number is negative</p>
  <p v-else-if="num > 0">v-else-if for number is positif</p>
  <p v-else >v-else for NOT A NUMBER</p>

  <h3 v-show="showElement">Using v-show attribute</h3>

</template>

<script>

export default {
  
  name: 'App',
  data(){
    return{
      name :"Vue3 projet",
      source  : "Code Evolution in youtube",
      html:"<b>Bold effet</b>",
      id: 'headId',
      disabled: false,
      highlight: "orange",
      style :{
        color : "#2fe2ae",
        fontWeight : "bold",
        widht: 200,
        border : "1px solid black"
      },
      num: 'a',
      showElement: true
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
