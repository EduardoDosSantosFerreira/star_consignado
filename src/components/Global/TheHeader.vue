<template>
  <header class="header">
    <!-- Logo -->
    <div class="logo">
      <a href="/">
        <img src="../../assets/img/starsemfundo.png" alt="Logo" />
      </a>
    </div>

    <!-- Botões (visíveis em telas maiores) -->
    <nav class="nav-desktop" v-if="!isMobile">
      <button class="nav-button" @click="goHome">Home</button>
      <button class="nav-button" @click="scrollToServices">Serviços</button>
      <button class="nav-button" @click="scrollToFaq">Perguntas Frequentes</button>
      <a href="https://wa.me/5521983192355?text=Olá,%20gostaria%20de%20mais%20informações!" target="_blank" class="contact-button">Fale Conosco</a>
    </nav>

    <!-- Menu Hambúrguer (visível em telas menores) -->
    <div class="hamburger" v-if="isMobile" @click="toggleMenu">
      <div class="hamburger-line"></div>
      <div class="hamburger-line"></div>
      <div class="hamburger-line"></div>
    </div>

    <!-- Menu Mobile (aparece ao clicar no hambúrguer) -->
    <nav class="nav-mobile" v-if="isMobile" :style="{ maxHeight: isMenuOpen ? '250px' : '0' }">
      <button class="nav-button" @click="goHome">Home</button>
      <button class="nav-button" @click="scrollToServices">Serviços</button>
      <button class="nav-button" @click="scrollToFaq">Perguntas Frequentes</button>
      <a href="https://wa.me/5521983192355?text=Olá,%20gostaria%20de%20mais%20informações!" target="_blank" class="contact-button">Fale Conosco</a>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      isMobile: false,
      isMenuOpen: false,
    };
  },
  methods: {
    checkScreenSize() {
      this.isMobile = window.innerWidth <= 768;
    },
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    },
    goHome() {
      window.location.href = '/';
    },
    scrollToServices() {
      const servicesSection = document.querySelector('.py-10.bg-gray-50');
      if (servicesSection) {
        servicesSection.scrollIntoView({ behavior: 'smooth' });
      }
      if (this.isMobile) {
        this.toggleMenu();
      }
    },
    scrollToFaq() {
      const faqSection = document.querySelector('#faq-section');
      if (faqSection) {
        faqSection.scrollIntoView({ behavior: 'smooth' });
      }
      if (this.isMobile) {
        this.toggleMenu();
      }
    },
  },
  mounted() {
    this.checkScreenSize();
    window.addEventListener('resize', this.checkScreenSize);
  },
  beforeDestroy() {
    window.removeEventListener('resize', this.checkScreenSize);
  },
};
</script>

<style scoped>
/* Estilos gerais do header */
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0.5rem 10vw;
  background-color: #0f0d0e;
  position: relative; /* Garante que o z-index funcione */
  z-index: 10; /* Fica acima de outras seções como hero-image */
}

/* Estilo do logo */
.logo img {
  height: 100px;
}

/* Estilo dos botões (desktop e mobile) */
.nav-button {
  font-weight: 500;
  border: none;
  color: #ffffff;
  margin: 0 0.75rem;
  cursor: pointer;
  font-size: 1rem;
  background: none;
}

.nav-button:hover {
  color: #5c5c5c;
}

/* Estilo do botão Fale Conosco */
.contact-button {
  font-weight: 600;
  color: #ffffff;
  background-color: #868686;
  padding: 0.5rem 1rem;
  border-radius: 5px;
  text-decoration: none;
  font-size: 1rem;
  margin: 0 0.75rem;
  display: inline-block;
  transition: background-color 0.3s ease;
}

.contact-button:hover {
  background-color: #1ebe52;
  color: #ffffff;
}

/* Estilo do menu hambúrguer */
.hamburger {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  width: 24px;
  height: 18px;
  cursor: pointer;
}

.hamburger-line {
  width: 100%;
  height: 2px;
  background-color: white; /* Melhor visibilidade em fundo escuro */
}

/* Estilo do menu mobile */
.nav-mobile {
  display: flex;
  flex-direction: column;
  position: absolute;
  top: 100px; /* Alinha abaixo do logo */
  right: 1rem;
  background-color: #000000;
  padding: 0 1rem;
  border-radius: 5px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  transition: max-height 0.3s ease, padding 0.3s ease;
  max-height: 0;
  overflow: hidden;
  z-index: 15; /* Garante que o menu fique acima da imagem de fundo */
}

.nav-mobile button,
.nav-mobile .contact-button {
  margin: 0.4rem 0;
  font-size: 1rem;
}

/* Responsividade */
@media (max-width: 768px) {
  .nav-desktop {
    display: none;
  }
}

@media (min-width: 769px) {
  .hamburger,
  .nav-mobile {
    display: none;
  }
}
</style>
