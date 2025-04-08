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
    </nav>

    <!-- Menu Hambúrguer (visível em telas menores) -->
    <div class="hamburger" v-if="isMobile" @click="toggleMenu">
      <div class="hamburger-line"></div>
      <div class="hamburger-line"></div>
      <div class="hamburger-line"></div>
    </div>

    <!-- Menu Mobile (aparece ao clicar no hambúrguer) -->
    <nav class="nav-mobile" v-if="isMobile" :style="{ maxHeight: isMenuOpen ? '200px' : '0' }">
      <button class="nav-button" @click="goHome">Home</button>
      <button class="nav-button" @click="scrollToServices">Serviços</button>
      <button class="nav-button" @click="scrollToFaq">Perguntas Frequentes</button>
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
  padding: 0.5rem 10vw; /* Reduzido de 1rem para 0.5rem */
  background-color: #0f0d0e;
}

/* Estilo do logo */
.logo img {
  height: 100px; /* Reduzido de 150px para 100px */
}

/* Estilo dos botões (desktop e mobile) */
.nav-button {
  font-weight: 500;
  border: none;
  color: rgb(255, 255, 255);
  margin: 0 0.75rem; /* Reduzido de 1rem para 0.75rem */
  cursor: pointer;
  font-size: 1rem; /* Reduzido de 1.25rem para 1rem */
}

.nav-button:hover {
  color: #5c5c5c;
}

/* Estilo do menu hambúrguer */
.hamburger {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  width: 24px; /* Reduzido de 28px para 24px */
  height: 18px; /* Reduzido de 22px para 18px */
  cursor: pointer;
}

.hamburger-line {
  width: 100%;
  height: 2px; /* Reduzido de 3px para 2px */
  background-color: rgb(35, 35, 35);
}

/* Estilo do menu mobile */
.nav-mobile {
  display: flex;
  flex-direction: column;
  position: absolute;
  top: 50px; /* Reduzido de 60px para 50px */
  right: 1rem;
  background-color: #000000;
  padding: 0 1rem;
  border-radius: 5px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  transition: max-height 0.3s ease, padding 0.3s ease;
  max-height: 0;
  overflow: hidden;
}

.nav-mobile button {
  margin: 0.4rem 0; /* Reduzido de 0.5rem para 0.4rem */
  font-size: 1rem; /* Reduzido de 1.1rem para 1rem */
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