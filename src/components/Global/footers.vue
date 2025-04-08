<template>
  <footer class="py-10 sm:pt-14 lg:pt-18">
    <div class="px-4 mx-auto sm:px-6 lg:px-8 max-w-7xl">
      <!-- Grid Principal -->
      <div class="grid grid-cols-1 gap-y-12 md:grid-cols-3 lg:grid-cols-4 gap-x-8">
        <!-- Seção de Descrição -->
        <div class="md:col-span-3 lg:col-span-2 lg:pr-8">
          <p class="text-base leading-relaxed text-white mt-4">
            Somos uma referência em soluções de crédito, utilizando tecnologia de ponta para aprimorar sua experiência
            conosco.
          </p>

          <!-- Redes Sociais -->
          <div class="mt-6">
            <h2 style="font-size: 1.2rem;" class="text-white text-sm font-semibold mb-2">Nos siga</h2>
            <br>
            <ul class="flex items-center space-x-4">
              <li v-for="social in socialLinks" :key="social.name">
                <a :href="social.url" :title="social.name"
                  class="flex items-center justify-center text-white text-2xl transition-all duration-200 bg-gray-800 rounded-full w-12 h-12 hover:bg-blue-600 focus:bg-blue-600">
                  <font-awesome-icon :icon="['fab', social.icon]" />
                </a>
              </li>
            </ul>
          </div>
        </div>

        <!-- Seção de Links: Serviços -->
        <div>
          <h3 class="text-lg font-semibold text-white">Serviços</h3>
          <ul class="mt-4 space-y-3">
            <li>
              <a href="/politicas-de-privacidade"
                class="text-base text-white transition-all duration-200 hover:text-blue-600 focus:text-blue-600">
                Política de Privacidade
              </a>
            </li>
            <li>
              <a href="/termos-de-uso"
                class="text-base text-white transition-all duration-200 hover:text-blue-600 focus:text-blue-600">
                Termos de Uso
              </a>
            </li>
          </ul>
        </div>

        <!-- Seção de Contato -->
        <div>
          <h3 class="text-lg font-semibold text-white">Fale Conosco</h3>
          <ul class="mt-4 space-y-3">
            <li class="flex items-center">
              <font-awesome-icon :icon="['fas', 'phone']" class="w-4 h-4 text-white mr-2" />
              <a href="tel:+2198319235555" class="text-base text-white hover:underline">21 98319-2355</a>
            </li>
            <li class="flex items-center">
              <font-awesome-icon :icon="['fas', 'envelope']" class="w-4 h-4 text-white mr-2" />
              <a href="mailto:Contato@starconsignados.com.br"
                class="text-base text-white hover:underline">Contato@starconsignados.com.br</a>
            </li>
            <li class="flex items-center">
              <font-awesome-icon :icon="['fas', 'map-marker-alt']" class="w-4 h-4 text-white mr-2" />
              <a href="https://www.google.com/maps/search/Travessa+Moura+S%C3%A1+n%C2%BA7+sala+701" target="_blank"
                class="text-base text-white hover:underline">
                Travessa Moura Sá n°7 sala 701
              </a>
            </li>
          </ul>
        </div>
      </div>

      <!-- Linha Divisória e Copyright -->
      <hr class="mt-12 mb-6 border-gray-200" />
      <p class="text-sm text-center text-white">
        © Direitos Autorais 2025, todos os direitos reservados
      </p>
      <br>
      <p style="color: white;">
        A Star Consignados não é uma instituição financeira e não realiza operações de crédito diretamente. A Star
        Consignados é uma plataforma digital que atua como correspondente bancário para facilitar o processo de
        contratação de empréstimos. Como correspondente bancário, seguimos as diretrizes do Banco Central do Brasil,
        conforme a Resolução CMN nº 4.935/2021 do BACEN.

        Toda avaliação de crédito é realizada de acordo com a política da Instituição Financeira escolhida pelo usuário.
        Antes da contratação de qualquer serviço por meio de nossos parceiros, você receberá todas as condições e
        informações relativas ao produto desejado de forma clara, completa e transparente.

        As taxas de juros, margem consignável e prazos de pagamento praticados nos empréstimos consignados para
        servidores públicos federais, estaduais e municipais, militares das Forças Armadas e beneficiários do INSS
        seguem as normas específicas de cada convênio, bem como a política de crédito da instituição financeira
        contratada.

        STAR CONSIGNADOS SOLUÇÕES EM CRÉDITO LTDA – CNPJ 56.950.767/0001-36
        Endereço: Travessa Moura Sá, nº 7 - Sala 701 - Madureira - Rio de Janeiro/RJ - CEP 21351-080
      </p>
    </div>

    <!-- Whatsapp Icon -->
    <a class="whatsapp-float" href="https://wa.me/5521983192355" target="_blank">
      <img alt="WhatsApp" src="https://upload.wikimedia.org/wikipedia/commons/6/6b/WhatsApp.svg" />
    </a>
  </footer>
</template>


<script>
// Importar o Font Awesome
import { library } from '@fortawesome/fontawesome-svg-core'
import { faPhone, faEnvelope, faMapMarkerAlt } from '@fortawesome/free-solid-svg-icons'
import { faFacebook, faInstagram } from '@fortawesome/free-brands-svg-icons'
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'

// Adicionar os ícones à biblioteca
library.add(faPhone, faEnvelope, faMapMarkerAlt, faFacebook, faInstagram)

export default {
  components: {
    FontAwesomeIcon
  },
  data() {
    return {
      socialLinks: [
        { name: 'Facebook', url: 'https://www.facebook.com/starconsignados/', icon: 'facebook' },
        { name: 'Instagram', url: 'https://www.instagram.com/starconsignados', icon: 'instagram' }
      ]
    };
  }
};
</script>

<style scoped>
/* Estilo base do footer */
footer {
  background-color: #0f0d0e;
  @apply border-t border-gray-200;
}

/* Título das seções */
h3 {
  @apply tracking-tight;
}

/* Animações dos links */
ul li a {
  @apply transition-all duration-200;
}

/* Responsividade */
@media (max-width: 768px) {
  footer {
    @apply py-8;
  }

  .grid {
    @apply gap-y-8;
  }
}

/* Ícone do WhatsApp flutuante */
.whatsapp-float {
  position: fixed;
  bottom: 20px;
  right: 20px;
  z-index: 1000;
}

.whatsapp-float img {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.3);
  transition: transform 0.3s ease-in-out;
}

.whatsapp-float img:hover {
  transform: scale(1.1);
}
</style>