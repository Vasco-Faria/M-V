<template>
<div class="t-shirts-container">
    <div class="t-shirts-wrapper">
        <Title text="Clothing" />
        <div class="content">
        <div class="image-container">
          <img src="/Sweat.jpeg" alt="T-shirt" class="rotated-image" />
        </div>
        <div class="text-container">
          <p>Descubra o estilo perfeito para as suas corridas e momentos de lazer. Conforto e atitude em cada detalhe.</p>
        </div>
      </div>

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
  width: 90%;
  justify-content: space-between;
  align-items: center;
  margin-top: 20px;
  color: white;
}

.image-container {
  flex: 1;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 10px;
}

.rotated-image {
  transform: rotate(-5deg);
  border: 10px solid white;
  padding: 5px;
  max-width: 60%;
  height: auto;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
}

.text-container {
  flex: 1;
  padding: 20px;
  text-align: left;
  font-size: 1.2rem;
  color: #fff;
}

</style>