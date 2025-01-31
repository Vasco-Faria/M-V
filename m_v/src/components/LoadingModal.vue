<template>
  <div v-if="isVisible" class="loading-container">
    <div class="overlay"></div>
    <div class="loadingModal">
      <img src="/logo.png" alt="Logo" class="logo" />
      <div class="loader"></div>
      <div class="loader-title2">Loading...</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "LoadingModal",
  props: {
    isVisible: Boolean, // Controla se o modal aparece ou não
  },
};
</script>

<style scoped>
.overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: transparent;
  z-index: 10003;
}

.logo{
  width: 100px;
  height: 100px;
  margin-bottom: 4em;
}

.loadingModal {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 18em;
  height: 10rem;
  display: flex;
  flex-direction: column;
  border-radius: 56px;
  justify-content: center;
  align-items: center;
  background-color: transparent;
  z-index: 9999;
}


.loader-title2 {
  color: rgb(255, 255, 255);
  margin-top: 2em;
  font-size: 20px;
  font-weight: bold;
}

/* HTML: <div class="loader"></div> */
.loader {
  color: #ffffff;
  width: 6px;
  aspect-ratio: 1;
  border-radius: 50%; 
  animation:
    l37-1 .75s infinite linear alternate,
    l37-2 1.5s  infinite linear; 
}
@keyframes l37-1 {
  0%,
  20% {box-shadow:30px 0 0 3px, 10px 0 0 3px, -10px 0 0 3px,-30px 0 0 3px}
  60%,
  100% {box-shadow:12px 0 0 3px, 14px 0 0 6px, -14px 0 0 6px,-12px 0 0 3px}
}

@keyframes l37-2 {
  0%,25%   {transform: rotate(0)}
  50%,100% {transform: rotate(.5turn)}
}

</style>
