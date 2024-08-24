<template>
  <div class="app">
    <div class="header-container">
      <div class="logo-container-main">
        <img class="logo-mobile" src="./assets/1.png" width="80" alt="logo">
        <img class="logo-desktop" src="./assets/4.png" width="200" alt="logo">
      </div>
      <div class="icon-container-main">
        <a href="https://www.facebook.com/Michelleferreirafotografia/" target="_blank" class="icon-link">
          <span class="icon-container">
            <i class="fab fa-facebook icon"></i>
          </span>
        </a>
        <a href="https://www.tiktok.com/@mi.mmy" target="_blank" class="icon-link">
          <span class="icon-container">
            <i class="fab fa-tiktok icon"></i>
          </span>
        </a>
        <a href="https://www.instagram.com/michelleferreirafotografiaa" target="_blank" class="icon-link">
          <span class="icon-container">
            <i class="fab fa-instagram icon"></i>
          </span>
        </a>
      </div>
      <div class="menu-container">
        <button class="menu-toggle" @click="toggleMenu">
          <div :class="{'bar': true, 'active': isActive}"></div>
          <div :class="{'bar': true, 'active': isActive}"></div>
          <div :class="{'bar': true, 'active': isActive}"></div>
        </button>
      </div>
      <div v-if="isActive" :class="{'menu': true, 'animate__animated': isActive, 'animate__fadeInRight': isActive}">
        <ul class="menu-list">
          <li><a href="#home" @click="scrollToSection('home')">HOME</a></li>
          <li><a href="#about" @click="scrollToSection('about')">QUEM SOU</a></li>
          <li><a href="#portfolio" @click="scrollToSection('portfolio')">PORTFOLIO</a></li>
          <li><a href="#contact" @click="scrollToSection('contact')">CONTATO</a></li>
        </ul>
      </div>
      <div class="navbar">
        <ul>
          <li><a href="#home" @click="scrollToSectionDesktop('home')">HOME</a></li>
          <li><a href="#about" @click="scrollToSectionDesktop('about')">QUEM SOU</a></li>
          <li><a href="#portfolio" @click="scrollToSectionDesktop('portfolio')">PORTFOLIO</a></li>
          <li><a href="#contact" @click="scrollToSectionDesktop('contact')">CONTATO</a></li>
        </ul>
      </div>
    </div>
    <div ref="home" class="home">
      <div class="home-image-container">
        <img src="./assets/home.jpg" width="100%" class="home-image" alt="home">
      </div>
      <div class="home-text">
        <div>
          <img src="./assets/1.png" width="80" alt="logo" class="home-logo">
        </div>
        <span class="home-title">MICHELLE</span>
        <span class="home-title">FERREIRA</span>
        <div class="home-subtitle">
          <div>
            <span> • FESTAS</span>
            <span> • EVENTOS</span>
          </div>
          <div>
            <span> • ANIVERSÁRIOS</span>
            <span> • CASAMENTOS</span>
          </div>
        </div>
      </div>
    </div>
    <div ref="about" class="about">
      <div class="about-image-container">
        <img src="./assets/aboutbg.png" width="100%" alt="about" class="about-bg-image">
        <img src="./assets/my.png" class="about-image-she-photo" alt="about">
      </div>
      <div class="about-right">
        <div class="about-title-container">
          <span class="about-title">
            Quem sou
          </span>
        </div>
        <div class="hifen"></div>
        <div class="about-text-container">
          <p class="about-text">
            Olá! Sou Michelle Ferreira da Silva, uma fotógrafa apaixonada por capturar a beleza e a emoção dos momentos cotidianos.
  Sempre fui apaixonada por uma boa foto, porém minha jornada na fotografia começou em 2021, quando comprei minha primeira câmera. <br> Em 2022 comecei estudar Fotografia pela [ Foto e Conceito ], onde desenvolvi uma compreensão profunda das técnicas fotográficas, composição e edição. Meses depois, comecei a fazer fotos em eventos, foi então que percebi o poder das imagens para contar histórias e despertar sentimentos.
  
  Minha abordagem é centrada em capturar momentos espontâneos e verdadeiros, onde busco capturar a autenticidade do momento enquanto adiciono um toque artístico. Prefiro trabalhar com luz natural para criar imagens que transmitam uma sensação de espontaneidade e verdade.” Acredito que cada imagem deve transmitir uma narrativa e emocionar o espectador.
  
  Quando não estou atrás da câmera, gosto de curtir a natureza, passear com meu Pet, aproveitar a família e fazer exercícios físicos.
  Adoro descobrir novos lugares e experiências que possam enriquecer meu olhar artístico.
  
  Sinta-se à vontade para explorar meu portfólio e me seguir nas redes sociais para acompanhar minhas últimas criações. Se você tem um projeto em mente ou simplesmente quer conversar sobre fotografia, não hesite em me contactar!
          </p>
        </div>
      </div>
    </div>
    <div v-if="expandedImage" class="expanded-image-overlay" 
      :class="['expanded-image-overlay', { show: showExpandedImage, hide: !showExpandedImage }]" 
      @click="closeExpandedImage"
    >
      <img :src="expandedImage" class="expanded-image" />
      <button class="close-button" @click="closeExpandedImage">X</button>
    </div>
    <div ref="portfolio" class="portfolio-container">
      <div class="portfolio-imgs">
        <div class="portfolio-image-first-container">
          <img src="./assets/portfolio/port1.jpg" class="portfolio-image" alt="portfolio" @click="expandImage(require('@/assets/portfolio/port1.jpg'))">
          <img src="./assets/portfolio/port2.jpg" class="portfolio-image" alt="portfolio" @click="expandImage(require('@/assets/portfolio/port2.jpg'))">
          <img src="./assets/portfolio/port3.jpg" class="portfolio-image" alt="portfolio" @click="expandImage(require('@/assets/portfolio/port3.jpg'))">
          <img src="./assets/portfolio/port4.jpg" class="portfolio-image" alt="portfolio" @click="expandImage(require('@/assets/portfolio/port4.jpg'))">
        </div>
        <div class="portfolio-image-second-container">
          <img src="./assets/portfolio/port5.jpg" class="portfolio-image" alt="portfolio" @click="expandImage(require('@/assets/portfolio/port5.jpg'))">
          <img src="./assets/portfolio/port6.jpg" class="portfolio-image" alt="portfolio" @click="expandImage(require('@/assets/portfolio/port6.jpg'))">
          <img src="./assets/portfolio/port7.jpg" class="portfolio-image" alt="portfolio" @click="expandImage(require('@/assets/portfolio/port7.jpg'))">
          <img src="./assets/portfolio/port8.jpg" class="portfolio-image" alt="portfolio" @click="expandImage(require('@/assets/portfolio/port8.jpg'))">
        </div>
        <div class="portfolio-image-third-container">
          <img src="./assets/portfolio/port9.jpg" class="portfolio-image" alt="portfolio" @click="expandImage(require('@/assets/portfolio/port9.jpg'))">
          <img src="./assets/portfolio/port10.jpg" class="portfolio-image" alt="portfolio" @click="expandImage(require('@/assets/portfolio/port10.jpg'))">
          <img src="./assets/portfolio/port11.jpg" class="portfolio-image" alt="portfolio" @click="expandImage(require('@/assets/portfolio/port11.jpg'))">
          <img src="./assets/portfolio/port12.jpg" class="portfolio-image" alt="portfolio" @click="expandImage(require('@/assets/portfolio/port12.jpg'))">
        </div>
      </div>
      <div class="portfolio-image-fourth-container">
        <img src="./assets/portfolio/port13.jpg" class="portfolio-final-image" alt="portfolio">
      </div>
      <div class="portfolio-image-fourth-container-text">
        <span class="portfolio-final-image-text">
          "A Fotografia é uma viagem as suas melhores recordações. 📸" 
        </span>
      </div>
    </div>
    <div ref="contact" class="contact-container">
      <div>
        <div class="contact-title-container">
          <span class="contact-title">Vamos conversar</span>
        </div>
        <div class="hifen"></div>
        <div class="inputs-container">
          <input type="text" class="name-input input-default" placeholder="Nome">
          <input type="text" class="email-input input-default" placeholder="Email">
          <input type="text" class="phone-input input-default" placeholder="Telefone">
          <textarea type="text" class="message-input textarea-default" placeholder="Mensagem"></textarea>
          <button class="contact-button">Enviar</button>
        </div>
      </div>
      <div>
        <img src="./assets/finaldesktopcontactimg.png" width="100" alt="contact-image" class="final-img-contact">
      </div>
    </div>
  </div>
</template>

<script>
import '@fortawesome/fontawesome-free/css/all.css';
import 'animate.css';

export default {
  name: 'App',
  components: {
    
  },

  data() {
    return {
      isActive: false,
      expandedImage: null,
    };
  },
  methods: {
    toggleMenu() {
      this.isActive = !this.isActive;
    },

    expandImage(imageSrc) {
      this.expandedImage = imageSrc;
      this.showExpandedImage = true
    },
    closeExpandedImage() {
      this.showExpandedImage = false;
      setTimeout(() => {
        this.expandedImage = null;
      }, 500);
    },

    scrollToSection(section) {
      const element = this.$refs[section];
      const start = window.pageYOffset;
      const end = element.getBoundingClientRect().top + window.pageYOffset;
      const duration = 600;
      let startTime = null;

      function animation(currentTime) {
        if (startTime === null) startTime = currentTime;
        const progress = Math.min((currentTime - startTime) / duration, 1);
        const easing = progress * (2 - progress);
        window.scrollTo(0, start + (end - start) * easing);
        if (progress < 1) {
          requestAnimationFrame(animation);
        }
      }

      requestAnimationFrame(animation);

      this.toggleMenu();
    },

    scrollToSectionDesktop(section) {
      const element = this.$refs[section];
      const start = window.pageYOffset;
      const end = element.getBoundingClientRect().top + window.pageYOffset;
      const duration = 600;
      let startTime = null;

      function animation(currentTime) {
        if (startTime === null) startTime = currentTime;
        const progress = Math.min((currentTime - startTime) / duration, 1);
        const easing = progress * (2 - progress);
        window.scrollTo(0, start + (end - start) * easing);
        if (progress < 1) {
          requestAnimationFrame(animation);
        }
      }

      requestAnimationFrame(animation);
    },
  },
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app {
  overflow-x: hidden;
}

.final-img-contact {
  display: none;
}

.header-container {
  display: flex;
  padding: 20px;
  justify-content: space-between;
  align-items: center;
  border-bottom: 1px solid gray;
}

.icon-container {
  background-color: white;
  padding: 15px;
  border-radius: 50%;
  margin: 0px 5px;
  border: 1px solid #ebbb3a;
}

.input-default {
  border: 1px solid #ebbb3a;
  border-radius: 5px;
  padding: 10px;
  margin: 10px 0;
  width: 100%;  
}

.textarea-default {
  border: 1px solid #ebbb3a;
  border-radius: 5px;
  padding: 10px;
  margin: 10px 0;
  width: 100%;
  resize: none;
  min-height: 200px;
}

.menu-list {
  list-style: none;
  padding: 0;
  margin: 0;
  font-family: 'Inria Serif', sans-serif;
  display: flex;
  flex-direction: column;
  font-size: 25px;
  align-items: center;
  margin-top: 150px;
  color: rgb(187, 187, 187);
}

.logo-desktop {
  display: none;
}

.menu-list li {
  margin: 10px 0;
}

.menu-list a {
  text-decoration: none;
  color: inherit;
}

.icon {
  color: #ebbb3a;
  font-size: 15px;
}

.app {
  position: relative;
}

.menu-toggle {
  display: flex;
  flex-direction: column;
  cursor: pointer;
  border: none;
  background: transparent;
  z-index: 5;
  position: relative;
}

.bar {
  width: 30px;
  height: 3px;
  background-color: #e0bc57;
  margin: 5px 0;
  transition: all 0.3s;
}

.bar.active:nth-child(1) {
  transform: rotate(45deg) translate(10px, 10px);
}

.bar.active:nth-child(2) {
  opacity: 0;
}

.bar.active:nth-child(3) {
  transform: rotate(-45deg) translate(7px, -8px);
}

.menu {
  position: absolute;
  background-color: white;
  min-width: 100%;
  height: 100%;
  bottom: 0;
  left: 0;
  right: 0;
  top: 0;
  display: flex;
  justify-content: center;
  z-index: 4;
}

.home-image-container {
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
  overflow: hidden;
}

.home-image {
  min-width: 160vw;
  max-height: 100%;
  opacity: 0.6;
  position: relative;
}

.home-text {
  display: flex;
  flex-direction: column;
  justify-content: center;
  text-align: center;
  font-family: 'Inria Serif', sans-serif;
  font-size: 40px;
  position: absolute;
  top: 15%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 100%;
  color: black;
}

.home-subtitle {
  font-size: 20px;
}

.about {
  position: relative;
  margin: 10px 0px 10px 10px;
}

.about-image-container {
  position: relative;
}

.about-bg-image {
  width: 100%;
}

.about-image-she-photo {
  position: absolute;
  bottom: 5px;
  left: 0;
  max-width: 180px;
}

.hifen {
  width: 10%;
  height: 1px;
  background-color: #333;
  margin-bottom: 20px
}

.about-title {
  font-family: 'Inria Serif', sans-serif;
  font-size: 30px;
  color: #5e5e5e;
}

.contact-container {
  margin: 20px 10px;
}

.contact-title {
  font-family: 'Inria Serif', sans-serif;
  font-size: 30px;
  color: #5e5e5e;
}

.about-title-container {
  margin-top: 20px;
  margin-bottom: 20px;
}

.contact-title-container {
  margin-top: 20px;
  margin-bottom: 20px;
}

.portfolio-image {
  width: 25vw;
  height: 20vw;
  object-fit: cover;
  display: flex;
}

.navbar {
  display: none;
}

.portfolio-image-first-container {
  display: flex;
}

.portfolio-image-second-container {
  display: flex;
}

.portfolio-image-third-container {
  display: flex;
}

.portfolio-final-image {
  width: 100vw;
  height: 60vw;
  object-fit: cover;
  display: flex;
  opacity: 0.4;
}

.portfolio-image-fourth-container-text {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
}

.portfolio-final-image-text {
  font-family: 'Inria Serif', sans-serif;
  font-size: 30px;
  position: absolute;
  bottom: 0;
  color: black;
  padding: 20px;
  font-weight: 800;
}

.expanded-image-overlay {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.8);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 10;
  opacity: 0;
  visibility: hidden;
  transition: opacity 0.5s ease, visibility 0.5s ease;
}

/* Aplica a animação de fade-in quando a classe show é adicionada */
.expanded-image-overlay.show {
  opacity: 1;
  visibility: visible;
  animation: fadeIn 0.5s ease-out;
}

/* Aplica a animação de fade-out quando a classe hide é adicionada */
.expanded-image-overlay.hide {
  opacity: 0;
  visibility: hidden;
  animation: fadeOut 0.5s ease-out;
}

.expanded-image {
  max-width: 90%;
  max-height: 90%;
  object-fit: contain;
}

.close-button {
  position: absolute;
  top: 20px;
  right: 20px;
  background: transparent;
  border: none;
  padding: 10px;
  cursor: pointer;
  font-size: 24px;
  color: white;
  font-weight: bold;
}

.about-text {
  color:#A0A09F;
}

.contact-button {
  font-family: 'Inria Serif', sans-serif;
  font-size: 20px;
  color: #5e5e5e;
  min-width: 100%;
  background-color: #ebbb3a;
  border: none;
  border-radius: 5px;
  padding: 10px 5px;
  text-decoration: none;
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

@keyframes fadeOut {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}

@media (min-width: 768px) {
  .menu-container {
    display: none;
  }

  .icon-container-main {
    position: fixed;
    display: flex;
    flex-direction: column;
    gap: 50px;
    top: 50vh;
    z-index: 10;
  }

  .icon-container {
    background-color: white;
    padding: 15px;
    border-radius: 50%;
    margin: 0px 5px;
    border: 1px solid #ebbb3a;
    z-index: 10;
  }

  .navbar {
    display: flex;
    justify-content: center;
  }

  .navbar ul {
    display: flex;
    gap: 20px;
    list-style: none;
  }

  .navbar a {
    text-decoration: none;
    color: #9b9b9b;
    font-size: 20px;
  }
  
  .header-container {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    background: linear-gradient(to bottom, black, transparent);
    padding: 2rem 2%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    z-index: 999;
    transition: .3s;
    border: none;
    color: white;
  }

  .header-container navbar ul li {
    z-index: 1000;
    color: white;
  }
  
  .logo-container-main .logo-mobile {
    display: none;
  }

  .logo-container-main .logo-desktop {
    display: block;
    padding: 5px;
    border-radius: 5px;
  }

  .home-image {
    min-width: 100vw;
    bottom: 0;
    filter: brightness(70%);
    position: fixed;
    z-index: -10;
    object-fit: cover;
    min-height: 100vh;
  }
  
  .home {
    height: 100vh;
  }

  .home-text {
    display: block;
    flex-direction: row;
    justify-content: center;
    text-align: center;
    font-family: 'Inria Serif', sans-serif;
    font-size: 70px;
    position: absolute;
    top: 10%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 100%;
    color: #ffffff;
  }

  .home-title {
    margin: 0px 5px;
  }
  
  .home-subtitle {
    font-size: 40px;
  }

  .home-logo {
    filter: contrast(200%);
  }

  .about {
    position: relative;
    margin: 0px 0px 0px 0px;
    display: flex;
  }

  .about-image-container {
    min-width: 50vw;
    object-fit: cover;
    display: flex;
  }


  .about-right {
    background-color: white;
    padding: 40px;
    min-width: 100vw;
  }

  .about-image-she-photo {
    position: absolute;
    right: 0;
    margin-left: 10%;
    object-fit: cover;
    min-width: 350px;
    display: flex;
  }

  .about-text {
    width: 40vw;
    max-height: 25vh;
    word-wrap: break-word;
  }
  

  .portfolio-image {
    transition: filter 1s ease;
  }

  .portfolio-image:hover {
    filter: brightness(190%);
  }

  .portfolio-final-image {
    opacity: 1;
    filter: brightness(60%);
  }

  .portfolio-imgs {
    padding-bottom: 20px;
    background-color: white;
  }

  .portfolio-final-image-text {
    color: white;
    font-size: 50px;
    max-width: 700px;
    margin-bottom: 50px;
  }
  
  .contact-container {
    background-color: white;
    margin: 0px 0px;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .inputs-container {
    width: 100%;
    padding: 0 120px;
  }

  .final-img-contact {
    display: flex;
    height: 100%;
    width: 100%;
    min-height: 100vh;
    object-fit: cover;
  }

  .contact-title, .hifen {
    margin-left: 120px;
  }

  .expanded-image-overlay, .expanded-image {
    z-index: 2000;
  }
}
</style>
