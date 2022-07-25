<template>
  
  <h2>My name is {{fullName }}</h2>
  <p> La moyenne des notes donne {{moyenne}} </p>
  <button @click="notes.push(10)">Add 10 to notes</button> <hr>
  <h1>Use v-for an v-if on the products list</h1>

  <template v-for="p in products" :key="p.id">
    <h2 v-if="p.price >500">{{p.name}} {{p.price}}</h2>
  </template>
  <hr>
  <h1>Use computed properties to filter a products table</h1>
  <template v-for="p in productsFilter" :key="p.id">
    <h2>{{p.name}} at {{p.price}}</h2>
  </template>
  <hr>

  <h2>{{fullName}}</h2>
  <button @click="changefullName">Change name</button>

</template>

<script>


export default {
  data(){
    return{
      lastName: "Dolched",
      firstName: "Gabanane",
      notes : [12,14,5,2,10,15,4,7.5,14,18,19,15,20,0,3,5,5],
      country : '',
      products:[
        {
          id: 1,
          name: 'Laptop',
          price: 1400
        },
        {
          id: 2,
          name: 'Smartphone',
          price: 500
        },
        {
          id: 3,
          name: 'Tablet',
          price: 700
        },
        {
          id: 4,
          name: 'Desktop',
          price: 1000
        },
      ]
    }
  },
  methods:{
    getfullName(){
      this.full = this.lastName+' '+this.firstName
      console.log(this.country);
    },
    changefullName(){
      this.fullName = 'Demon King'
    },
  },
  computed: {
    fullName:{
      get(){
        return this.lastName+' '+this.firstName
      },
      set(value){
        const names = value.split(' ')
        this.lastName = names[0]
        this.firstName = names[1]
      }
    },
    moyenne(){
      var moy=0;
      for(var i in this.notes){
        moy+=this.notes[i]
      }
      return moy/this.notes.length;
    },
    productsFilter(){
      return this.products.filter(p => p.price > 500)
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
