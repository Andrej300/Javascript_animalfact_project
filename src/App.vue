<template> 
  <div>
   <h1> Animals </h1>
  <div class="app">
    <animals-list :animals="animals"></animals-list>
    <animal-detail :animal ='selectedAnimal'></animal-detail>
   </div>
  </div>
</template>

<script>

import { eventBus } from './main.js'
import AnimalsList from './components/AnimalsList.vue';
import AnimalDetail from './components/AnimalDetail.vue';

export default {
  name: 'App',
  data() {
    return {
   animals: [
        {name:'Dog',weight:30, group:'Mammal', nutrition: 'Carnivorous'},
        {name:'Cat', weight:5, group:'Mammal', nutrition: 'Carnivorous'},
        {name:'Tiger',weight:200, group:'Mammal', nutrition: 'Carnivorous'},
        {name:'Elephant',weight:6000, group:'Mammal', nutrition: 'Herbivorous'},
        {name:'Chicken',weight:2, group:'Bird', nutrition: 'Herbivorous'},
        {name:'Mouse',weight:1, group:'Mammal', nutrition: 'Omnivorous'},
        {name:'Lion',weight:250, group:'Mammal', nutrition: 'Carnivorous'},
        {name:'Monkey',weight:50, group:'Mammal', nutrition: 'Omnivorous'},
        {name:'Giraffe',weight:800, group:'Mammal', nutrition:'Herbivorous'},
        {name:'Snake',weight:510, group:'Fish', nutrition: 'Carnivorous'},
        {name:'Dolphin',weight:160, group:'Fish', nutrition: 'Carnivorous'},
        {name:'Crocodile',weight:400, group:'Reptiles', nutrition: 'Carnivorous'},
        {name:'Eagle',weight:10, group:'Birds', nutrition: 'Carnivorous'},
        {name:'Stork',weight:8, group:'Bird', nutrition: 'Carnivorous'},
        {name:'Ant',weight:1, group:'Invertebrate', nutrition: 'Omnivorous'},
        {name:'Horse',weight:550, group:'Mammal', nutrition: 'Herbivorous'}
        
      ],
      selectedAnimal: null
    };
  },
  components: {
    "animals-list": AnimalsList,
    "animal-detail": AnimalDetail
  },


mounted () {
  eventBus.$on('selected-animal',(animal)=> {
    this.selectedAnimal = animal
  })
}
}
</script>

<style lang="css" scoped>
  h1 {
    text-align: center;
    color:blue;
  }
  .app {
    display: flex;
    justify-content: space-between;
    width: 90%;
    margin: 0 auto;
  }
</style>