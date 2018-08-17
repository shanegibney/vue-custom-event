<template lang="html">
  <div>
    <h1>This is the child component</h1>
    <div v-for="(individual, index) in people" :key="index">
      <span @click="remove(individual.name)">{{ index+1 }}.  {{ individual.name }}</span>
    </div>
    <div>
      <h1> <a href="https://github.com/shanegibney/vue-custom-event">Return to repo</a> </h1>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Child',
  props: ['people'],
  data(){
    return {}
  },
  methods: {
    remove(name){
      this.$emit('remove', {name})
    }
  }
}
</script>

<style lang="css">
h1 {
   color: #444;
}
</style>
