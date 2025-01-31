<template>
  <LoadingModal v-if="loading" :isVisible="loading" />
  <div class="app2">
    <div class="special-message" v-if="!loading">
      <h1>Miles And Vibes 👋</h1>
      <p>Este website está disponível apenas para desktop. <br> Para mais informações, visite o nosso Linktr.ee.</p>
      <Button label="Linktr.ee" @click="redirectToLinktree"></Button>
    </div>

    <Navbar v-if="!loading"
      :scrollToHome="() => scrollToSection('home')"
      :scrollToAbout="() => scrollToSection('aboutus')"
      :scrollToTshirts="() => scrollToSection('tshirts')"
      :scrollToGroups="() => scrollToSection('groups')"
    />
    
    <div class="basic-container" v-show="!loading" id="basicContainer">
      <Home id="home" />
      <AboutUs id="aboutus" />
      <tshirts id="tshirts"/>
      <groups id="groups"/>
      <Footer />
    </div>
  </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import Home from "./components/Home.vue";
import AboutUs from "./components/AboutUs.vue";
import LoadingModal from "./components/LoadingModal.vue";
import Footer from "./components/Footer.vue";
import tshirts from "./components/tshirts.vue";
import groups from "./components/groups.vue";
import Button from "./components/Button.vue";

export default {
  components: {
    Navbar,
    Home,
    AboutUs,
    LoadingModal,
    Footer,
    tshirts,
    groups,
    Button,
  },
  data() {
    return {
      loading: true,
    };
  },
  mounted() {
    // Remover o modal depois de 2 segundos
    setTimeout(() => {
      this.loading = false;
    }, 2000);
    this.$nextTick(() => {
      // Adicionando log para verificar se o id 'home' está acessível
      console.log(document.getElementById('home')); // Verifique se o id 'home' é encontrado
    });
  },
  methods: {
    scrollToSection(sectionId) {
      this.$nextTick(() => {
        // Garantir que o DOM foi atualizado
        const container = document.getElementById('basicContainer');
        const section = document.getElementById(sectionId);

        if (container && section) {
          container.scrollTo({
            top: section.offsetTop - container.offsetTop,
            behavior: "smooth",
          });
        } else {
          console.error(`Elemento com o id ${sectionId} não encontrado.`);
        }
      });
    },
    redirectToLinktree() {
      window.open("https://linktr.ee/seu_link", "_blank");
    }
  }
};
</script>


<style scoped>
.app2 {
  width: 100%;
  height: 100%;
  background-color: transparent;
  padding-top: 18vh !important;
}

/* Mensagem especial para telas menores */
.special-message {
  display: none;
  text-align: center;
  margin-top: 20vh;
}

.special-message h1 {
  font-size: 2rem;
  margin-bottom: 15px;
  color: #5e5e5e;
}

.special-message p {
  font-size: 1.2rem;
  line-height: 1.5;
  color: #ddd;
  margin-bottom: 20px;
}

.basic-container {
  display: flex;
  justify-content: flex-start;
  align-items: center;
  flex-direction: column;
  width: 100%;
  height: 100vh;
  background-color: transparent;
  margin: 0 auto;
  overflow-y: auto;
  gap: 7vh;
  flex-grow: 1;
}

.basic-container > * {
  width: 100%;
  min-height: 75vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

/* Ajuste para o componente Home, para garantir que ele ocupe o espaço disponível */
.basic-container > home {
  flex-grow: 1;
  display: flex;
  justify-content: center;
  align-items: center;
}

/* Ajuste do componente Footer para garantir que ele se comporte corretamente */
.basic-container > *:last-child {
  height: auto;
  min-height: 10vh;
  flex-grow: 0;
}

.basic-container > *:last-child {
  margin-bottom: 15vh;
}

/* Media Query para telas menores que 1500px */
@media (max-width: 1500px) {
  .basic-container,
  .navbar,
  .app2 > *:not(.special-message):not(.loading-modal) {
    display: none;
  }

  .special-message {
    display: block;
    font-size: 2rem;
    color: #333;
  }

  /* Estilo específico para o LoadingModal */
  .loading-modal {
    display: block !important; /* Garante que o modal apareça em telas pequenas */
  }
}
</style>
