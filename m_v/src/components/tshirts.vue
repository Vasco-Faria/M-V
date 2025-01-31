<template>
<div class="t-shirts-container">
    <div class="t-shirts-wrapper">
        <Title text="T-shirts" />
    </div>
</div>
</template>

<script>
import Title from "./Title.vue";

export default {
  name: "tshirts",
  components: {
    Title,
  },
}
</script>


<style scoped>
.t-shirts-container {
  width: 100%;
  height: 75vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.t-shirts-wrapper {
  width: 80%;
  display: flex;
  height: 100%;
  margin: auto auto;
  justify-content: center;
  align-items: center;
  position: relative;
  flex-direction: column;
}

.content {
  display: flex;
  width: 100%;
  justify-content: space-between;
  align-items: center;
  margin-top: 20px;
  color: white;
}

</style>