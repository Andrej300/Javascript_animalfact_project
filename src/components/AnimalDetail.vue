
<template lang="html">
    <div v-if="animal" id="animalDetail">
        <div id="detailWrapper">
            <h2>{{animal.name}}</h2>
            <div id="flexWrapper">
            <div id="left">
            
                <h3><span>Weight</span> {{ animal.weight }}</h3>
                <h3><span>Group</span> {{ animal.group }}</h3>
                 <ul v-for="group in animal.group"></ul>
  </div>
  <div id="right">
  </div>
  </div>
</div>
</div>
</template>


<script>
export default {
    name: "animal-detail",
    props: ['animal']
}
</script>

<style lang="css" scoped>
#animalDetail {
    box-sizing: border-box;
    height: 400px;
    width: 60%;
    background: rgb(193, 31, 31);
    color: rgb(13, 14, 13);
    padding: 10px;
    border: 1px solid rgb(59, 138, 34);
  }

  #detailWrapper {
    box-sizing: border-box;
    background: #fff;
    padding: 10px;
    height: 100%;
    border-radius: 3px;
  }

  #flexWrapper {
    display: flex;
    justify-content: space-between;
  }

  #left, #right {
    width: 100;
  }

  #right img {
    width: 100%;
  }

  #left p:first-child {
    margin-top: 0;
  }

  h2 {
    margin: 10px 0 20px;
    padding: 0;
  }

  p span {
    font-weight: bold;
  }

</style>