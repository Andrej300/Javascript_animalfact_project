
<template lang="html">
    <div v-if="animal" id="animalDetail">
        <div id="detailWrapper">
            <h2>{{animal.name}}</h2>
            <div id="flexWrapper">
            <div id="left">
            
                <h3><span>Weight:</span> {{ animal.weight }}</h3>
                <h3><span>Group:</span> {{ animal.group }}</h3>
                <h3><span>Nutrition:</span>{{animal.nutrition}}</h3>
                
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
    width: 30%;
    background: rgb(193, 31, 31);
    color: rgb(13, 14, 13);
    padding: 10px;
    border: 10px solid rgb(59, 138, 34);
    border-radius: 10px;
    margin:20px
  }

  #detailWrapper {
    box-sizing: border-box;
    background:rgb(224, 191, 191);
    padding: 10px;
    height: 100%;
    border-radius: 3px;
  }

  #flexWrapper {
    display: flex;
    justify-content: space-around;
  }

  #left, #right {
    width: 50;
  }

  #right {
    width: 10%;
  }

  #left {
    margin: 50;
  }

  h2 {
    margin:30px 0 20px;
    padding: 10;
  }
  h3 {
      margin: 50px 0 20px;
  }

  p span {
    font-weight: bold;
  }

</style>