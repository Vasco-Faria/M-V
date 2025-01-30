<template>
 <Navbar />
 <div class="basic-container">
  <Home/>
  <AboutUs/>
 </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import Home from "./components/Home.vue";
import AboutUs from "./components/AboutUs.vue";

export default {
  components: {
    Navbar,
    Home,
    AboutUs,
  },
};
</script>

<style scoped>

.basic-container{
  display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    width: 100%;
    min-height: 77vh;
    background-color: transparent;
    margin: 0 auto;
    margin-top: 20vh !important;
    overflow-y: auto;
    padding-top: 50vh;
}

</style>
