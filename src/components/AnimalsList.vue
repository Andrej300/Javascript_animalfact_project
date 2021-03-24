<template lang="html">
  <div id="animalsList">
        <ul>
          <list-component v-for="(animal, index) in animals" :animal="animal" :key="index"></list-component>
      </ul>
  </div>
</template>

<script>
import ListComponent from './ListComponent.vue';

export default {
 name: 'animals-list',
 props: ['animals'],
 components: {
     "list-component": ListComponent
 }
}
</script>

<style lang="css" scoped>
#animalsList {
    background:rgb(219, 98, 98);
    height: 400px;
    width: 400px;
    overflow-y: scroll;
    border: 10px solid rgb(26, 129, 12);
    border-radius: 10px;
    margin: 20px;
  }

  #animalsList ul {
    margin: 10px;
    padding: 0;
  }

  ::-webkit-scrollbar {
    -webkit-appearance:none;
    width: 8px;
  }

  ::-webkit-scrollbar-thumb {
    border-radius: 10px;
    background-color: rgba(66, 20, 174, 0.5);
    -webkit-box-shadow: 0 0 1px rgba(13, 132, 23, 0.5);
  }
</style>
