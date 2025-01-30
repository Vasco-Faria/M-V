<template>
   <div class="home-container">
    <div class="content">
      <h1 class="title">Miles And Vibes</h1>
      <p class="subtitle">Run Community & Club 🏃🫡 🔫 In a mission to join people all over the world to run! </p>
    </div>

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
    import { faFacebookF, faInstagram, faWhatsapp, faTelegram } from "@fortawesome/free-brands-svg-icons";
    import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";

    library.add(faFacebookF, faInstagram, faWhatsapp,faTelegram);


export default {
    name: "Home",
    components: {
        FontAwesomeIcon,
    },
    data(){
        return {
            socialLinks: [
        { name: "Facebook", url: "https://www.facebook.com", icon: "facebook-f", class: "facebook" },
        { name: "Instagram", url: "https://www.instagram.com", icon: "instagram", class: "instagram" },
        { name: "WhatsApp", url: "https://wa.me/seunumerodetelefone", icon: "whatsapp", class: "whatsapp" },
        { name: "Telegram", url: "https://t.me/seunome", icon: "telegram", class: "telegram" }
      ]
        }
    }

}
</script>

<style scoped>
.home-container {
  width: 100%;
  min-height: 77vh;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  position: relative;
  text-align: center;
  color: white;
}


.content {
  max-width: 80%;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  padding-bottom: 5em;

}

.title {
  font-size: 4rem;
  font-weight: bold;
  margin: 0;
}

.subtitle {
  font-size: 1.5rem;
  opacity: 0.8;
}


.icon {
  font-size: 2rem;
  text-decoration: none;
  color: white;
  transition: transform 0.3s ease-in-out;
}

.icon:hover {
  transform: scale(1.2);
}

.custom-text {
  position: absolute;
  bottom: 20px;
  right: 20px;
  text-decoration: none;
  font-size: 1rem;
  opacity: 0.8;
  cursor: pointer;
}

.custom-text:after {
    content: "";
    position: absolute;
    bottom: -2px;
    left: 0;
    width: 0;
    height: 2px;
    background-color: white;
    transition: width 0.3s ease-in-out;
  }
  
  .custom-text:hover::after {
    width: 100%;
  }


.basr-social-share {
  position: absolute;
  bottom: 20px;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
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
</style>