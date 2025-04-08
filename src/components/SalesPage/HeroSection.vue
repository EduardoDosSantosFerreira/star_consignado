<template>
  <section class="hero-section">
    <div class="overlay"></div>
    <img
      class="hero-image"
      src="../../assets/img/gptimage.png"
      alt="Imagem do Hero Section"
    />

    <div class="text-content">
      <p class="tagline">Conte com a Star Consignados</p>
      <h1>Seu Crédito Consignado de Forma Rápida e Segura!</h1>
      <p class="subtitle">
        Oferecemos as melhores condições para você acessar seu crédito consignado sem burocracia. Realize seus planos com segurança e confiança!
        <br />
        (+ de 10.000 clientes satisfeitos)
      </p>

      <div class="cta-links">
        <a 
  href="https://wa.me/5521983192355?text=Olá,%20gostaria%20de%20mais%20informações!" 
  target="_blank" 
  class="cta-link"
>
  Saiba Mais <span>↗</span>
</a>
        <a href="https://api.whatsapp.com/send/?phone=5521983192355&text=Olá,%20gostaria%20de%20simular%20meu%20crédito%20consignado!" target="_blank" class="whatsapp-link">
          <i class="fab fa-whatsapp"></i> Fale Conosco
        </a>
      </div>
    </div>
  </section>
</template>



<script>
export default {
  name: "HeroSection",
  mounted() {
    // Adicionando a classe 'visible' após 100ms para que a animação de fade aconteça
    setTimeout(() => {
      this.$refs.tagline.classList.add("visible");
      this.$refs.title.classList.add("visible");
      this.$refs.subtitle.classList.add("visible");
      this.$refs.heroImage.classList.add("visible");
    }, 100); // Atraso de 100ms para permitir que o conteúdo seja renderizado antes da animação
  },
};
</script>

<style scoped>
.hero-section {
  position: relative;
  height: 700px; /* Altura menor */
  width: 100%;
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: flex-start;
  color: white;
  background-color: white; /* Fundo branco visível abaixo da imagem */
}

.hero-image {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 110%;
  object-fit: cover;
  z-index: 1;
}

.overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(to right, rgba(0, 0, 0, 0.95), rgba(0, 0, 0, 0.3), rgba(0, 0, 0, 0));
  z-index: 2;
}

.text-content {
  position: relative;
  z-index: 3;
  max-width: 600px;
  padding-left: 4rem;
  padding-right: 2rem;
}

.tagline {
  font-size: 1rem;
  color: #f9b233;
  text-transform: uppercase;
  margin-bottom: 1rem;
  font-weight: bold;
}

h1 {
  font-size: 3rem;
  font-weight: 700;
  line-height: 1.2;
  margin-bottom: 1rem;
}

.subtitle {
  font-size: 1.1rem;
  font-weight: 300;
  line-height: 1.6;
  margin-bottom: 2rem;
}

.cta-links {
  display: flex;
  align-items: center;
  gap: 1.5rem;
}

.cta-link {
  color: #f9b233;
  font-weight: bold;
  text-decoration: none;
  border-bottom: 2px solid #f9b233;
  padding-bottom: 2px;
}

.whatsapp-link {
  color: white;
  text-decoration: none;
  font-weight: 500;
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.whatsapp-link i {
  font-size: 1.2rem;
}

/* Responsividade */
@media (max-width: 768px) {
  .text-content {
    padding: 2rem;
    max-width: 100%;
  }

  h1 {
    font-size: 2rem;
  }

  .subtitle {
    font-size: 1rem;
  }

  .cta-links {
    flex-direction: column;
    align-items: flex-start;
    gap: 1rem;
  }
}

@media (max-width: 768px) {
  .hero-section {
    height: auto;
    padding-top: 3rem;
    padding-bottom: 3rem;
    flex-direction: column;
    justify-content: center;
  }

  .hero-image {
    height: 100%;
    object-position: center;
  }

  .overlay {
    background: linear-gradient(to bottom, rgba(0, 0, 0, 0.85), rgba(0, 0, 0, 0.3), rgba(0, 0, 0, 0));
  }

  .text-content {
    padding: 1.5rem;
    text-align: center;
    max-width: 100%;
  }

  .tagline {
    font-size: 0.9rem;
  }

  h1 {
    font-size: 1.8rem;
    line-height: 1.3;
  }

  .subtitle {
    font-size: 0.95rem;
    line-height: 1.5;
  }

  .cta-links {
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 1rem;
  }

  .cta-link,
  .whatsapp-link {
    font-size: 0.95rem;
  }
}


</style>