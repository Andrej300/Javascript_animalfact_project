<template lang="html">
  <li v-on:click="handleClick">{{animal.name}}</li>
</template>

<script>
import { eventBus } from '../main.js'

export default {
    name: 'list-component',
    props: ['animal'],
    methods: {
        handleClick: function() {
            eventBus.$emit('selected-animal', this.animal);
        }
    }
}
</script>

<style lang="css" scoped>
li {
    list-style-type: none;
    display: block;
    background: rgb(72, 165, 29);
    font-size: 18px;
    margin: 5px 0;
    padding: 5px;
    cursor: grab;
    color: rgb(30, 25, 25);
    transition: 0.1s all ease-in;
    border-radius: 3px;
  }

  li:hover {
    background: #8da8d7;
    color: rgb(106, 51, 51);
  }


</style>