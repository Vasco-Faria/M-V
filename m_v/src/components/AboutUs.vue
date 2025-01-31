<template>
<div class="aboutus-container">
  <div class="aboutus-wrapper">
    <Title text="AboutUs" />
    <div class="content">
      
    </div>
  </div>
</div>
</template>

<script>


import Title from "./Title.vue";
export default {
    name: "AboutUs",
    components: {
      Title,
    }
}
</script>

<style scoped>
.aboutus-container {
  width: 100%;
  height: 84vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.aboutus-wrapper{
  width: 80%;
  display: flex;
  height: 100%;
  margin: auto auto;
  justify-content: center;
  align-items: center;
  position: relative;
}

</style>