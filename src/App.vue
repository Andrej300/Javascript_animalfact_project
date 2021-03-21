<template>
  <div id="app">
    <animals-list :animals="animals"></animals-list>
    <animal-detail :animal ='selectedAnimal'></animal-detail>
    <h1> Hello </h1>
  </div>
</template>

<script>
import AnimalsList from './components/AnimalsList.vue';
import AnimalDetail from './components/AnimalDetail.vue';

export default {
  name: 'App',
  data() {
    return {
   animals: [
        {name: "snake", weight: 5},
        {name: "dog", weight: 25},
      ],
      selectedAnimal: null
    };
  },
  components: {
    "animals-list": AnimalsList,
    "animal-detail": AnimalDetail
  }
}
</script>

<style>
#app {

}
</style>