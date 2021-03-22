
<template lang="html">
    <div v-if='animal'>
  <h2>{{ animal.name }}</h2>
  <h3>Weight: {{ animal.weight }}</h3>
  <h3>Group: {{ animal.group.toLocaleString() }}</h3>
  </div>
</template>


<script>
export default {
    name: "animal-detail",
    props: ['animal']
}
</script>

<style lang="css" scoped>

</style>