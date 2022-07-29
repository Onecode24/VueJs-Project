<template>
  <h3>Greet World Components</h3>
  <GreetWorld name="Angelo" pseudo="onecode24"/>
  <GreetWorld :name="name" :pseudo="pseudo"/>
  <h3>Article cards components</h3>
  <ArticleCards title="Article 1" :likes="10" :isUpdated="true"/>
  <ArticleCards title="Article 2" :likes="20" :isUpdated="false"/>

</template>

<script>
import GreetWorld from './components/Greet-world.vue'
import ArticleCards from './components/Article-cards.vue'

export default {
  name: 'App',
  components: {
    GreetWorld,
    ArticleCards,
  },
  data(){
    return{
      name: 'Belmonde',
      pseudo:'belcloud41'
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
h3{
  color: #000000;
}
</style>
