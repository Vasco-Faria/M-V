<template>
    <nav class="navbar">
      <!-- Links à esquerda -->
      <ul class="nav-links left">
        <li><p>Home</p></li>
        <li><p>About Us</p></li>
      </ul>
  
      <!-- Logo -->
      <img src="/logo.png" alt="Logo" class="logo" />
  
      <!-- Links à direita -->
      <ul class="nav-links right">
        <li><p>T-shirts</p></li>
        <li><p>Search your city</p></li>
      </ul>
  
      <!-- Hamburger Menu -->
      <div class="hamburger" @click="toggleMenu">
        <span class="bar"></span>
        <span class="bar"></span>
        <span class="bar"></span>
      </div>
    </nav>
  
        <!-- Menu Lateral (full screen) -->
    <div v-if="menuOpen" class="side-menu background" :class="{ open: menuOpen }">
        <div class="close-btn" @click="toggleMenu">X</div>
        <img src="/logo.png" alt="Logo" class="side-logo" />
        <ul class="side-links">
        <li><p>Home</p></li>
        <li><p>About Us</p></li>
        <li><p>T-shirts</p></li>
        <li><p>Search your city</p></li>
        </ul>
        <div class="basr-social-share social">
            <ul>
            <li v-for="(social, index) in socialLinks" :key="index">
                <a :href="social.url" target="_blank" :class="social.class">
                <font-awesome-icon :icon="['fab', social.icon]" />
                <span>{{ social.name }}</span>
                </a>
            </li>
            </ul>
        </div>
    </div>
  </template>
  
  <script>

    import { library } from "@fortawesome/fontawesome-svg-core";
    import { faFacebookF, faInstagram, faWhatsapp } from "@fortawesome/free-brands-svg-icons";
    import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";

    library.add(faFacebookF, faInstagram, faWhatsapp);
  export default {
    name: "Navbar",
    components: {
        FontAwesomeIcon,
    },
    data() {
      return {
        menuOpen: false,
            socialLinks: [
            { name: "Facebook", url: "https://www.facebook.com", icon: "facebook-f", class: "facebook" },
            { name: "Instagram", url: "https://www.instagram.com", icon: "instagram", class: "instagram" },
            { name: "WhatsApp", url: "https://wa.me/seunumerodetelefone", icon: "whatsapp", class: "whatsapp" }
            ]
        };
    },
    methods: {
      toggleMenu() {
        this.menuOpen = !this.menuOpen;
      }
    }
  };
  </script>
  
  <style scoped>
  /* Navbar fixa no topo com fundo transparente */
  .navbar {
    position: fixed;
    top: 0;
    left: 50%;
    transform: translateX(-50%);
    width: 60%;
    height: 10vh;
    margin-top: 2rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 15px 30px;
    background: transparent;
    z-index: 1000;
  }
  
  /* Logo */
  .logo {
    position: absolute;
    left: 50%;
    transform: translateX(-50%);
    font-size: 1.5rem;
    font-weight: bold;
    color: white;
    height: 150px;
  }
  
  /* Navbar Links */
  .nav-links {
    list-style: none;
    display: flex;
    gap: 20px;
    margin: 0;
    padding: 0;
    background-color: transparent;
    height: 100%;
    align-items: center;
    width: 25vw;
    text-align: center;
    justify-content: space-around;
  }
  
  /* Links à esquerda (alinhados à esquerda) */
  .nav-links.left {
    margin-right: auto;
  }
  
  /* Links à direita (alinhados à direita) */
  .nav-links.right {
    margin-left: auto;
  }
  
  .nav-links li {
    height: 75%;
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
    cursor: pointer;
  }
  
  /* Efeito da borda ao passar o mouse */
  .nav-links li::after {
    content: "";
    position: absolute;
    bottom: 0;
    left: 0;
    width: 0;
    height: 2px;
    background-color: white;
    transition: width 0.3s ease-in-out;
  }
  
  .nav-links li:hover::after {
    width: 100%;
  }
  
  .nav-links li p {
    text-decoration: none;
    color: white;
    font-size: 1.1rem;
    transition: color 0.3s ease;
  }
  
  .nav-links li p:hover {
    color: #ddd; /* Cor ao passar o mouse */
    cursor: pointer;
  }
  
  /* Estilo do hamburger menu */
  .hamburger {
    display: none;
    flex-direction: column;
    justify-content: space-between;
    width: 30px;
    height: 25px;
    cursor: pointer;
  }
  
  .hamburger .bar {
    width: 100%;
    height: 4px;
    background-color: white;
    transition: all 0.3s ease;
  }
  
  .side-menu {
  position: fixed;
  top: 0;
  left: -100%; /* Começa fora da tela à esquerda */
  width: 100%;
  height: 100%;
  background-color: #222;
  z-index: 1001;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 30px;
  box-shadow: inset 10px 0px 15px rgba(255, 255, 255, 0.548), 
    inset -10px 0px 15px rgba(255, 255, 255, 0.548);
  opacity: 0; /* Começa invisível */
  transition: left 0.5s ease, opacity 0.5s ease; /* Animações de posição e opacidade */
}

/* Quando o menu está aberto */
.side-menu.open {
  left: 0; /* Menu desliza para a posição correta */
  opacity: 1; /* Fica visível */
}
  
  .side-menu .side-logo {
    height: 150px;
  }
  
  /* Botão de fechar o menu */
  .close-btn {
    position: absolute;
    top: 20px;
    right: 20px;
    font-size: 2rem;
    color: white;
    cursor: pointer;
  }
  
  /* Links do Menu Lateral */
  .side-links {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 20px;
    margin: 0;
    padding: 0;
    color: white;
    text-align: center;
    z-index: 1002;
    transition: width 0.3s ease-in-out;
    position: relative;
  }


  .side-links li {
  position: relative; /* Ensure that the li is positioned */
  padding-bottom: 2px; /* Espaçamento para o efeito do sublinhado */
  cursor: pointer;
}
    
  /* Efeito da borda ao passar o mouse */
  .side-links li::after {
    content: "";
    position: absolute;
    bottom: 0;
    left: 0;
    width: 0;
    height: 2px;
    background-color: white;
    transition: width 0.3s ease-in-out;
  }
  
  .side-links li:hover::after {
    width: 100%;
  }
  
  .side-links li p {
    font-size: 1.5rem;
    cursor: pointer;
  }
  
  .side-links li p:hover {
    color: #ddd;
  }

  .side-menu-background {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5); /* Cor de fundo com opacidade */
  opacity: 0;
  z-index: 1000;
  transition: opacity 0.5s ease;
}

.side-menu-background.open {
  opacity: 1; /* Fundo fica visível */
}

.basr-social-share {
  width: 100%;
  display: flex;
  justify-content: center;
  text-align:center;
  padding:0 auto;
}

.basr-social-share a svg {
  font-size: 25px;
  margin-top: 0.70em;
  margin-left: 0.1em;
}

.social ul {
  list-style: none;
  padding-left: 0;
  padding-right: 0;
}

.social ul li:nth-child(1) {
    margin-left: 0;
}

.social ul li {
  border: 5px solid #ffffff;
  border-radius: 50%;
  float: left;
  position: relative;
  margin-left: 1em;
  width: 50px;
  height: 50px;
  text-align: center;
  -webkit-transition: all 0.3s ease 0s;
  -moz-transition: all 0.3s ease 0s;
  -o-transition: all 0.3s ease 0s;
  transition: all 0.3s ease 0s;
}
@media only screen and (max-width: 480px) {
  .social ul li {
    border-width: 4px;
    width: 45px;
    height: 45px;
  }
}
.social ul li:not(:last-child) {
  margin-right: 10px;
}
.social ul li:before {
  content: '';
  border-radius: 50%;
  -webkit-shadow: inset 0 0px 3px rgba(149, 90, 42, 0.28), 0px 0px 0px 2px rgba(149, 90, 42, 0.28);
  -ms-box-shadow: inset 0 0px 3px rgba(149, 90, 42, 0.28), 0px 0px 0px 2px rgba(149, 90, 42, 0.28);
  box-shadow: inset 0 0px 3px rgba(149, 90, 42, 0.28), 0px 0px 0px 2px rgba(149, 90, 42, 0.28);
  display: block;
  position: absolute;
  top: 50%;
  left: 50%;
  -webkit-transform: translate(-50%, -50%);
  -ms-transform: translate(-50%, -50%);
  -o-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
  width: 60px;
  height: 60px;
  opacity: 0.35;
  -webkit-transition: all 0.3s ease 0s;
  -moz-transition: all 0.3s ease 0s;
  -o-transition: all 0.3s ease 0s;
  transition: all 0.3s ease 0s;
}
@media only screen and (max-width: 480px) {
  .social ul li:before {
    width: 43px;
    height: 43px;
  }
}
.social ul li:hover {
  border-color: #a33629;
  -webkit-transition: all 0.3s ease 0s;
  -moz-transition: all 0.3s ease 0s;
  -o-transition: all 0.3s ease 0s;
  transition: all 0.3s ease 0s;
}
.social ul li:hover:before {
  -webkit-shadow: inset 0 0px 3px rgba(163, 54, 41, 0.28), 0px 0px 0px 2px rgba(163, 54, 41, 0.28);
  -ms-box-shadow: inset 0 0px 3px rgba(163, 54, 41, 0.28), 0px 0px 0px 2px rgba(163, 54, 41, 0.28);
  box-shadow: inset 0 0px 3px rgba(163, 54, 41, 0.28), 0px 0px 0px 2px rgba(163, 54, 41, 0.28);
  -webkit-transition: all 0.3s ease 0s;
  -moz-transition: all 0.3s ease 0s;
  -o-transition: all 0.3s ease 0s;
  transition: all 0.3s ease 0s;
}
.social ul li:hover i {
  color: #d66557;
  -webkit-stroke-width: 5.3px;
  -webkit-stroke-color: #a33629;
  -webkit-fill-color: #a33629;
  text-shadow: 1px 0px 20px #a33629;
  -webkit-transition: all 0.3s ease 0s;
  -moz-transition: all 0.3s ease 0s;
  -o-transition: all 0.3s ease 0s;
  transition: all 0.3s ease 0s;
}
.social ul li a {
  border-radius: 50%;
  display: block;
  position: absolute;
  top: -5px;
  left: -5px;
  width: 60px;
  height: 60px;
  line-height: 60px;
}
@media only screen and (max-width: 480px) {
  .social ul li a {
    background-size: cover;
    top: -5px;
    left: -5px;
    width: 45px;
    height: 45px;
    line-height: 45px;
  }
}
.social ul li a:before {
  content: '';
  background-image: url('https://img.picload.org/image/dcocwcga/border-social-hover.png');
  border-radius: 50%;
  display: block;
  position: absolute;
  top: 50%;
  left: 50%;
  width: 46px;
  height: 45px;
  -webkit-transform: translate(-50%, -50%);
  -ms-transform: translate(-50%, -50%);
  -o-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
  z-index: -1;
  opacity: 0;
  -webkit-transition: all 0.3s ease 0s;
  -moz-transition: all 0.3s ease 0s;
  -o-transition: all 0.3s ease 0s;
  transition: all 0.3s ease 0s;
}
@media only screen and (max-width: 480px) {
  .social ul li a:before {
    background-size: cover;
    width: 30px;
    height: 30px;
  }
}
.social ul li a:after {
  content: '';
  background-image: url('https://img.picload.org/image/dcocwcgd/border-social.png');
  border-radius: 50%;
  display: block;
  position: absolute;
  top: 50%;
  left: 50%;
  width: 46px;
  height: 45px;
  -webkit-transform: translate(-50%, -50%);
  -ms-transform: translate(-50%, -50%);
  -o-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
  z-index: -1;
  -webkit-transition: all 0.3s ease 0s;
  -moz-transition: all 0.3s ease 0s;
  -o-transition: all 0.3s ease 0s;
  transition: all 0.3s ease 0s;
}
@media only screen and (max-width: 480px) {
  .social ul li a:after {
    background-size: cover;
    width: 30px;
    height: 30px;
  }
}
.social ul li a:hover:before {
  opacity: 1;
  -webkit-transform: translate(-50%, -50%) rotate(360deg);
  -ms-transform: translate(-50%, -50%) rotate(360deg);
  transform: translate(-50%, -50%) rotate(360deg);
  -webkit-transition: all 0.3s ease;
  -moz-transition: all 0.3s ease;
  -o-transition: all 0.3s ease;
  transition: all 0.3s ease;
}
.social ul li a:hover:after {
  opacity: 0;
  -webkit-transform: translate(-50%, -50%) rotate(360deg);
  -ms-transform: translate(-50%, -50%) rotate(360deg);
  transform: translate(-50%, -50%) rotate(360deg);
  -webkit-transition: all 0.3s ease;
  -moz-transition: all 0.3s ease;
  -o-transition: all 0.3s ease;
  transition: all 0.3s ease;
}
.social ul li a i {
  color: #ffead3;
  font-size: 23px;
  font-weight: 900;
  position: absolute;
  top: 50%;
  left: 50%;
  -webkit-transform: translate(-50%, -50%);
  -ms-transform: translate(-50%, -50%);
  -o-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
  -webkit-stroke-width: 5.3px;
  -webkit-stroke-color: #ffead3;
  -webkit-fill-color: #ffead3;
  text-shadow: 1px 0px 20px #ffead3;
  -webkit-transition: all 0.3s ease 0s;
  -moz-transition: all 0.3s ease 0s;
  -o-transition: all 0.3s ease 0s;
  transition: all 0.3s ease 0s;
}
@media only screen and (max-width: 480px) {
  .social ul li a i {
    font-size: 16px;
  }
}
.social ul li a i.fa-envelope {
  font-size: 14px;
  top: 48%;
}
.k2t-footer.dark-style .social li a,
.dark-style .social li a {
  color: #fff;
}
.k2t-footer.dark-style .social li a:hover,
.dark-style .social li a:hover {
  color: #fff;
}
.basr-social-share.social li:hover a {
  color: #898989;
}
.basr-social-share.social li a {
  border-width: 0;
  color: #cccccc;
}
.basr-social-share.social li a:hover {
  color: #898989;
}
.basr-social-share.social li a span {
  display: none;
}
  
  /* Estilos para telas menores que 1400px */
  @media (max-width: 1400px) {
    .nav-links {
      display: none;
    }

    .navbar {
      width: 100%;
      padding: 0 50px;
      left: 0;
      transform: none;
      justify-content: space-between;
    }
  
    .hamburger {
      display: flex;
      margin-left: 2em;
    }

    .logo {
      right: 1em;
      left: none;
      transform: none;
      font-size: 1rem;
      height: 100px;
    }
  }
  
  /* Estilos para telas menores que 768px */
  @media (max-width: 768px) {
    .navbar {
      width: 100%;
      left: 0;
      transform: none;
      justify-content: space-between;
    }
  
    .logo {
      right: 1em;
      transform: none;
      font-size: 1rem;
      height: 100px;
    }
  }
  </style>
  