<template>
  <footer class="py-10 sm:pt-14 lg:pt-18">
    <div class="px-4 mx-auto sm:px-6 lg:px-8 max-w-7xl">
      <!-- Grid Principal -->
      <div class="grid grid-cols-1 gap-y-12 md:grid-cols-3 lg:grid-cols-4 gap-x-8">
        <!-- Seção de Descrição -->
        <div class="md:col-span-3 lg:col-span-2 lg:pr-8">
          <p class="text-base leading-relaxed text-white mt-4">
            Somos uma referência em soluções de crédito, utilizando tecnologia de ponta para aprimorar sua experiência conosco.
          </p>
          <!-- Redes Sociais -->
          <ul class="flex items-center space-x-4 mt-6">
            <li v-for="social in socialLinks" :key="social.name">
              <a :href="social.url" :title="social.name"
                class="flex items-center justify-center text-white transition-all duration-200 bg-gray-800 rounded-full w-8 h-8 hover:bg-blue-600 focus:bg-blue-600">
                <font-awesome-icon :icon="['fab', social.icon.replace('fa-', '')]" />
              </a>
            </li>
          </ul>
        </div>

        <!-- Seção de Links: Suporte -->
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
              <font-awesome-icon icon="phone" class="w-4 h-4 text-white mr-2" />
              <span class="text-base text-white">21 983192355</span>
            </li>
            <li class="flex items-center">
              <font-awesome-icon icon="envelope" class="w-4 h-4 text-white mr-2" />
              <span class="text-base text-white">Contato@starconsignados.com.br</span>
            </li>
            <li class="flex items-center">
              <font-awesome-icon icon="map-marker-alt" class="w-4 h-4 text-white mr-2" />
              <span class="text-base text-white">Travessa Moura Sá n°7 sala 701</span>
            </li>
          </ul>
        </div>
      </div>

      <!-- Linha Divisória e Copyright -->
      <hr class="mt-12 mb-6 border-gray-200" />
      <p class="text-sm text-center text-white">
        © Direitos Autorais 2025, todos os direitos reservados
      </p>
    </div>
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
        { name: 'Facebook', url: 'https://www.facebook.com/starconsignados/', icon: 'fa-facebook' },
        { name: 'Instagram', url: 'https://www.instagram.com/starconsignados', icon: 'fa-instagram' },
      ],
    };
  },
};
</script>

<style scoped>
/* Ajustes finos */

footer {
  background-color: #0f0d0e;
}

footer {
  @apply border-t border-gray-200;
}

h3 {
  @apply tracking-tight;
}

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
</style>
  