<template lang="html">
  <li v-on:click="handleClick">{{animal.name}}</li>
</template>

<script>
import { eventBus } from '../main.js'

export default {
    name: 'list-component',
    props: ['animal'],
    // methods: {
    //     handleClick: function() {
    //         eventBus.$emit('selected-animal', this.animal);
    //     }
    // }
}
</script>

<style lang="css" scoped>

</style>