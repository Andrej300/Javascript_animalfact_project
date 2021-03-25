<template lang ="html">
  <div>
   <h1> Animals </h1>
  <div class="app">
    <animals-list :animals="animals"></animals-list>
    <animal-detail :animal ='selectedAnimal'></animal-detail>
    <animal-picture :dogpic ='dogpic'></animal-picture>
   </div>
  </div>
</template>

<script>

import { eventBus } from './main.js'
import AnimalsList from './components/AnimalsList.vue';
import AnimalDetail from './components/AnimalDetail.vue';
import AnimalPicture from './components/AnimalPicture.vue';

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
      selectedAnimal: null,
      dogpic: null, 
    };
  },
  components: {
    "animals-list": AnimalsList,
    "animal-detail": AnimalDetail,
    "animal-picture": AnimalPicture
  },


mounted () {
  fetch('https://dog.ceo/api/breeds/image/random')
    .then(res => res.json())
    .then(dogpic => this.dogpic = dogpic.message)
    
    eventBus.$on('selected-animal',(animal)=> {
    this.selectedAnimal = animal
    fetch('https://dog.ceo/api/breeds/image/random')
    .then(res => res.json())
    .then(dogpic => this.dogpic = dogpic.message)

 
    })

}
}
</script>


<style lang="css" scoped>
  h1 {
    text-align: center;
    color:rgb(1, 1, 10);
    background-color:rgb(182, 106, 106);
    padding:15px;
    border:10px solid green;
    border-radius:3px;
  }
  .app {
    background-color: rgb(216, 195, 168);
    padding:1px;
    /* border: 10px solid rgb(223, 147, 147); */
    border-radius:1px;
    display: flex;
    justify-content: space-between;
    width: 100%;
    margin: -6px;
  
    
  }
 


</style>