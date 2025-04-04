<template>
  <section class="hero-section">
    <div class="container">
      <div class="grid">
        <!-- Texto e Call to Action -->
        <div class="text-content">
          <p class="tagline fade" ref="tagline">Conte com a Star Consignados</p>
          <h1 class="fade" ref="title">Seu Crédito Consignado de Forma Rápida e Segura!</h1>
          <h4 class="fade" ref="subtitle">
            Oferecemos as melhores condições para você acessar seu crédito consignado sem burocracia. Realize seus planos com segurança e confiança!
          </h4>

          <!-- Avaliações -->
          <div class="review">
            <span class="reviews-count">(+ de 10.000 clientes satisfeitos)</span>
          </div>

          <!-- Botão de Call to Action -->
          <a href="https://api.whatsapp.com/send/?phone=5521983192355&text=Olá,%20gostaria%20de%20simular%20meu%20crédito%20consignado!" target="_blank">
            <button class="cta-button">FALE CONOSCO</button>
          </a>
        </div>

        <!-- Imagem -->
        <div class="image-wrapper">
          <img class="hero-image fade" ref="heroImage" src="@/assets/img/STARanimado.gif" alt="Imagem do Hero Section" />
        </div>
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
  }
};
</script>

<style scoped>
.hero-section {
  background-color: #0f0d0e;
  background-size: cover;
  background-position: center;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 80vh;
  padding: 4rem 0;
  overflow: hidden;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
}

.container {
  max-width: 1500px;
  margin: 0 auto;
  padding: 0 20px;
}

.hero-image {
  width: 1200px;
  border-radius: 8px;
  transition: transform 0.3s ease;
}

.grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 2rem;
  align-items: center;
}

@media (min-width: 768px) {
  .grid {
    grid-template-columns: 1fr 1fr;
  }
}

.text-content {
  text-align: left;
  color: white;
}

.tagline {
  font-size: 1rem;
  font-weight: 500;
  color: #ffffff;
  margin-bottom: 0.5rem;
  text-transform: uppercase;
  letter-spacing: 1px;
}

h1 {
  font-size: 3rem;
  font-weight: 700;
  line-height: 1.2;
  margin-bottom: 1.5rem;
  color: #ffffff;
}

h4 {
  font-size: 1.25rem;
  font-weight: 400;
  line-height: 1.6;
  margin-bottom: 2rem;
  color: #ffffff;
}

.review {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  margin-bottom: 2rem;
}

.reviews-count {
  font-size: 1rem;
  color: #ffffff;
  font-weight: 500;
}

.cta-button {
  background-color: #adadad;
  color: black;
  font-weight: 700;
  font-size: 1rem;
  padding: 12px 24px;
  border-radius: 8px;
  border: none;
  cursor: pointer;
  transition: background-color 0.3s ease, transform 0.3s ease;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.cta-button:hover {
  background-color: #ffffff;
  transform: scale(1.05);
}

/* Adicionando o fade no CSS */
.fade {
  opacity: 0;
  transition: opacity 1s ease-in-out;
}

.fade.visible {
  opacity: 1;
}

@media (max-width: 768px) {
  .hero-section {
    height: auto;
    padding: 2rem 0;
  }

  h1 {
    font-size: 2rem;
    margin-top: 1rem;
  }

  h4 {
    font-size: 1rem;
  }

  .cta-button {
    width: 100%;
    padding: 12px 0;
  }
}
</style>
