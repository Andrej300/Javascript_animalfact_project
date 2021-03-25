<template lang="html">
    <div id="animalPicture">
           <img :src=dogpic id="dogs"/>
            

</div>
</template>



<script>
export default {
    name: "animal-picture",
    props: ['dogpic']
}
</script>

<style lang="css" scoped>

#dogs {
    
    
    width: 20vw;
    display: flex;
    justify-content: space-between;
    
  } 
  

</style> 