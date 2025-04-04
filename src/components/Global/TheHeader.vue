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
      isMobile: false, // Controla se está em modo mobile
      isMenuOpen: false, // Controla se o menu mobile está aberto
    };
  },
  methods: {
    // Verifica o tamanho da tela e atualiza o estado de isMobile
    checkScreenSize() {
      this.isMobile = window.innerWidth <= 768; // Define 768px como breakpoint para mobile
    },
    // Alterna a visibilidade do menu mobile
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    },
    // Redireciona para a página inicial
    goHome() {
      window.location.href = '/';
    },
    // Faz o scroll suave para o componente Services
    scrollToServices() {
      const servicesSection = document.querySelector('.py-10.bg-gray-50');
      if (servicesSection) {
        servicesSection.scrollIntoView({ behavior: 'smooth' });
      }
      if (this.isMobile) {
        this.toggleMenu(); // Fecha o menu mobile após clicar
      }
    },
    // Faz o scroll suave para o componente Faq
    scrollToFaq() {
      const faqSection = document.querySelector('#faq-section'); // Alterado para usar o ID
      if (faqSection) {
        faqSection.scrollIntoView({ behavior: 'smooth' });
      }
      if (this.isMobile) {
        this.toggleMenu(); // Fecha o menu mobile após clicar
      }
    },
  },
  mounted() {
    // Verifica o tamanho da tela ao carregar o componente
    this.checkScreenSize();
    // Adiciona um listener para verificar o tamanho da tela ao redimensionar a janela
    window.addEventListener('resize', this.checkScreenSize);
  },
  beforeDestroy() {
    // Remove o listener ao destruir o componente para evitar memory leaks
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
  padding: 1rem 10vw;
  background-color: #0f0d0e;
}

/* Estilo do logo */
.logo img {
  height: 150px; /* Reduzi um pouco aqui também para harmonia */
}

/* Estilo dos botões (desktop e mobile) */
.nav-button {
  font-weight: 500;
  border: none;
  color: rgb(255, 255, 255);
  margin: 0 1rem;
  cursor: pointer;
  font-size: 1.25rem; /* Reduzido de 1.50rem */
}

.nav-button:hover {
  color: #5c5c5c;
}

/* Estilo do menu hambúrguer */
.hamburger {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  width: 28px;
  height: 22px;
  cursor: pointer;
}

.hamburger-line {
  width: 100%;
  height: 3px;
  background-color: rgb(35, 35, 35);
}

/* Estilo do menu mobile */
.nav-mobile {
  display: flex;
  flex-direction: column;
  position: absolute;
  top: 60px;
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
  margin: 0.5rem 0;
  font-size: 1.1rem; /* Reduzido também para o mobile */
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
