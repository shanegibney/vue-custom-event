<template>
  <div id="app">
    <h1>I am the parent component</h1>
    <h2>Custom event</h2>
    <Child :people="people" @remove="removePeople"/>
  </div>
</template>

<script>
import Child from './components/Child'
export default {
  name: 'App',
  components: {
    Child
  },
  data(){
    return {
      title: 'people',
      people: [
        {name:'Bessy', age:'15'},
        {name:'Billy', age:'25'},
        {name:'Barbara', age:'35'},
        {name:'Bob', age:'45'}
      ]
    }
  },
  methods: {
    removePeople(payload){
      // console.log(payload);
      this.people=this.people.filter(individual=>{
        return individual.name!== payload.name
      })
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444;
  margin-top: 60px;
}
</style>
