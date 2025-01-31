<template>
  <div class="app2">
  <LoadingModal :isVisible="loading" />
 <Navbar v-if="!loading" />
 <div class="basic-container">
  <Home v-if="!loading" />
  <AboutUs v-if="!loading"/>
  <Footer v-if="!loading"/>
 </div>
</div>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import Home from "./components/Home.vue";
import AboutUs from "./components/AboutUs.vue";
import LoadingModal from "./components/LoadingModal.vue";
import Footer from "./components/Footer.vue";


export default {
  components: {
    Navbar,
    Home,
    AboutUs,
    LoadingModal,
    Footer,
  },
  data() {
    return {
      loading: true, 
    };
  },
  mounted() {
    // Remove o modal depois de 2 segundos
    setTimeout(() => {
      this.loading = false;
    }, 2000);
  },
};
</script>

<style scoped>

.app2{
  width: 100%;
  height: 100%;
  background-color: transparent;
  padding-top:18vh !important;
  padding-bottom: 5vh !important;
}

.basic-container{
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    width: 100%;
    height: calc(100vh - 14vh);
    background-color: transparent;
    margin: 0 auto;
    overflow-y: auto !important;
    gap: 3vh;
}

.basic-container > * {
    width: 100%;
    min-height: 100vh; /* Cada componente ocupa a tela toda */
    display: flex;
    justify-content: center;
    align-items: center;
}

.basic-container > *:last-child {
    width: 100%;
    height: 10vh;
    min-height: 10vh; /* Ou qualquer valor desejado */
}

</style>
