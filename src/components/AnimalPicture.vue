<template lang="html">
    <div id="animalPicture">
           <img :src=dogpic>
            <!-- <img src = "https://images.dog.ceo/breeds/schnauzer-giant/n02097130_5121.jpg"/> -->
            

</div>
</template>



<script>
export default {
    name: "animal-picture",
    props: ['dogpic']
}
</script>

<style lang="css" scoped>

#animalPicture {
    /* box-sizing: border-box;
    height: 400px;
    width: 70%;
    background: rgb(233, 220, 220);
    color: rgb(13, 14, 13);
    padding: 10px;
    border: 10px solid rgb(59, 138, 34);
    border-radius: 10px;
    margin:20px  */
    
  } 
  

</style> 