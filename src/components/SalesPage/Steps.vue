<template>
  <section class="container">
      <div class="px-4 mx-auto sm:px-6 lg:px-8 max-w-7xl">
          <div class="grid grid-cols-1 lg:grid-cols-2 gap-y-12">
              <div class="mt-12 flex flex-col justify-between lg:order-2">
                  <div class="flex-1">
                      <span class="badge"> O que você está esperando? </span>
                      <h1 class="title">Planos com o saque aniversário do FGTS.</h1>
                      <p class="description">O saque aniversário do FGTS pode ser o primeiro passo para realizar os seus maiores projetos. Venha descobrir como podemos ajudar você a alcançar suas metas.</p>
                      <a href="https://api.whatsapp.com/send/?phone=5521983192355&text=Ol%C3%A1,%20gostaria%20de%20simular%20meu%20saldo%20FGTS!" title="" class="button" role="button">
                          Quero saber mais
                      </a>
                  </div>
              </div>

              <div class="lg:order-1">
                  <div class="relative w-full max-w-sm mx-auto">
                      <!-- Substituindo o iframe do vídeo pela imagem -->
                      <img src="../../assets/img/executivo.jpg" alt="Imagem ilustrativa do FGTS" class="relative w-full max-w-xs mx-auto sm:max-w-sm rounded-2xl">
                  </div>
              </div>
          </div>
      </div>
  </section>
</template>

<script>
export default {
name: 'HeroSection',
};
</script>

<style scoped>
.container {
padding: 0 2rem;
}

img {
width: 100%; /* Respeita o contêiner pai */
height: auto; /* Ajusta a altura automaticamente para manter a proporção */
max-height: 100%; /* Evita ultrapassar o contêiner */
}

.badge {
display: inline-flex;
align-items: center;
padding: 0.5rem 0.75rem;
font-size: 0.875rem; /* 14px */
font-weight: 500;
color: #3b82f6; /* text-blue-600 */
border-radius: 1rem; /* rounded-xl */
background-color: #eff6ff; /* bg-blue-50 */
}

.title {
margin-top: 0.75rem; /* mt-3 */
margin-bottom: 2rem; /* Espaço pequeno entre título e descrição (corrigido de 9.5rem) */
font-size: 3rem; /* text-4xl */
font-weight: 600; /* font-semibold */
color: #111827; /* text-gray-900 */
}

.description {
font-size: 1.125rem; /* text-lg */
line-height: 1.75rem; /* leading-7 */
color: #374151; /* text-gray-700 */
margin-bottom: 1rem; /* Espaço reduzido entre descrição e botão */
}

.button {
display: inline-flex;
align-items: center;
justify-content: center;
padding: 1rem 2rem; /* px-8 py-4 */
font-size: 1rem; /* text-base */
font-weight: 500; /* font-medium */
color: rgb(255, 255, 255); /* text-white */
transition: all 0.2s; /* transition-all duration-200 */
background-color: #000000; /* bg-blue-600 */
border: none; /* border border-transparent */
border-radius: 1rem; /* rounded-xl */
}

.button:hover {
background-color: #ffffff; /* hover:bg-blue-700 */
color: #000000;
}

.button:focus {
outline: none; /* focus:outline-none */
ring: 2px; /* focus:ring-2 */
ring-offset: 2px; /* focus:ring-offset-2 */
ring-color: #1d4ed8; /* focus:ring-blue-700 */
}

/* Media query para mobile (telas menores que 640px) */
@media (max-width: 639px) {
section {
  padding-top: 2rem; /* py-8 em vez de py-12 */
  padding-bottom: 2rem;
}

img {
  height: 400px; /* Ajusta a altura da imagem para dispositivos móveis */
}

.badge {
  padding: 0.375rem 0.625rem; /* Menor padding */
  font-size: 0.75rem; /* 12px */
}

.title {
  margin-top: 0.5rem; /* mt-2 */
  margin-bottom: 0.375rem; /* Espaço ainda menor */
  font-size: 1.875rem; /* text-3xl em vez de 4xl */
}

.description {
  font-size: 1rem; /* text-base em vez de lg */
  line-height: 1.5rem; /* leading-6 */
  margin-bottom: 0.75rem; /* Espaço reduzido */
}

.button {
  padding: 0.75rem 1.5rem; /* Menor padding: px-6 py-3 */
  font-size: 0.875rem; /* 14px */
}
}
</style>