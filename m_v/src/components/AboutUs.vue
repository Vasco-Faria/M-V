<template>
  <div class="aboutus-container">
    <div class="aboutus-wrapper">
      <Title text="About Us" />
      
      <div class="content">
        <div class="text-column">
          <p>Somos uma comunidade apaixonada por corrida, conectando pessoas do mundo inteiro através do desporto.</p>
          <p>Junta-te a nós e faz parte desta jornada!</p>
          <p>ISTO CLARAMENTE PRECISA UM TEXTO</p>
        </div>

        <div class="image-column">
          <div class="image-slider">
            <img :src="images[currentImageIndex]" alt="Gallery Image" />
          </div>
        </div>
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
  },
  data() {
    return {
      images: [
        "/Wallpaper.jpeg",
        "/img2.jpeg",
        "/img3.jpeg",
        "/img1.jpeg"
      ],
      currentImageIndex: 0,
    };
  },
  mounted() {
    this.startImageChange();
  },
  methods: {
    startImageChange() {
      setInterval(() => {
        this.currentImageIndex = (this.currentImageIndex + 1) % this.images.length;
      }, 3000);  // Troca a imagem a cada 3 segundos
    },
  },
};
</script>

<style scoped>
.aboutus-container {
  width: 100%;
  height: 75vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.aboutus-wrapper {
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
  width: 80%;
  justify-content: space-between;
  align-items: center;
  margin-top: 20px;
  color: white;
}

.text-column {
  width: 45%;
  text-align: left;
}

.image-column {
  width: 45%;
  height: auto; /* Remove altura fixa */
  position: relative;
  overflow: hidden;
}

.image-slider img {
  width: 60%;
  height: auto; /* Altura proporcional */
  object-fit: cover; /* Garantir que a imagem cubra sem distorcer */
  transition: opacity 1s ease-in-out;  /* Transição suave entre as imagens */
}
</style>
