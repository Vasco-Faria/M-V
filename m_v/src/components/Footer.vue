<template>
    <footer class="footer">
      <div class="footer-left">
        <div class="left-top">
            <img src="/logo.png" alt="Logo" class="logo">
            <Button label="Strava Club" style="white-space: nowrap; margin-top: 0; margin-left: 1em;"></Button>
        </div>
        <div class="left-bottom">
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
      </div>
      <div class="footer-right">
        <a href="https://vascomfaria.com/" target="_blank" rel="noopener noreferrer">Made by Vasco Faria</a>
      </div>
    </footer>
  </template>
  
  <script>

import { library } from "@fortawesome/fontawesome-svg-core";
import { faFacebookF, faInstagram, faWhatsapp, faTelegram, faTiktok } from "@fortawesome/free-brands-svg-icons";
    import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";

    library.add(faFacebookF, faInstagram, faWhatsapp,faTelegram,faTiktok);


    import Button from "./Button.vue";


  export default {
    name: "Footer",
    components: {
        FontAwesomeIcon,
        Button,
    },
    data(){
        return {
            socialLinks: [
        { name: "Facebook", url: "https://www.facebook.com", icon: "facebook-f", class: "facebook" },
        { name: "Instagram", url: "https://www.instagram.com/milesandvibes_runclub/", icon: "instagram", class: "instagram" },
        { name: "TikTok", url: "https://wa.me/seunumerodetelefone", icon: "tiktok", class: "tiktok" },
        { name: "Telegram", url: "https://t.me/seunome", icon: "telegram", class: "telegram" }
      ]
        }
    }
  };
  </script>
  
  <style scoped>
  .footer {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 15vh !important;
    background-color: transparent;
    color: white;
    padding-bottom: 5vh;
  }
  
  .footer-left {
    height: 100%;
    display: flex;
    flex-direction: row;
    width: 35%;
    
  }
  



  .left-top{
    text-align: end;
    display: flex;
    align-items: center;
    justify-content: space-around;  
    width: 30%;
  }

  .logo {
  height: 60px; /* Ajusta conforme necessário */
  width: auto;
}
  

  .left-bottom{
    width: 70%;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .text {
  font-size: 16px; /* Ajusta o tamanho do texto */
  color: white; /* Define a cor do texto */
}

  .footer-right {
    width: 25%;
    height: 100%;
    
    text-align: end;
    display: flex;
    align-items: center;
    justify-content: flex-end;    
  }

  .footer-right a {
    text-decoration: none;
    cursor: pointer;
    color: inherit; /* Herda a cor do pai, removendo o azul padrão */
}


  .footer-right a:hover{
    text-decoration: underline;
  }


.basr-social-share {
  display: flex;
  flex-direction: row;
  gap: 10px;
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

@media (max-width: 1500px) {
  .social {
    display: none;
  }
}
  </style>
  