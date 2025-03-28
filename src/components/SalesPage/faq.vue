<template>
  <section class="py-5 bg-gray-50 sm:py-16 lg:py-24">
    <div id="faq-section" class="px-4 mx-auto sm:px-6 lg:px-8 max-w-7xl">
      <div class="max-w-2xl mx-auto text-center">
        <h2 class="text-3xl font-bold leading-tight text-black sm:text-4xl lg:text-5xl">
          Perguntas Frequentes
        </h2>
      </div>

      <div class="max-w-3xl mx-auto mt-8 space-y-4 md:mt-16">
        <div
          v-for="(faq, index) in faqs"
          :key="index"
          class="transition-all duration-200 bg-white border border-gray-200 shadow-lg cursor-pointer hover:bg-gray-50"
        >
          <button
            type="button"
            class="flex items-center justify-between w-full px-4 py-4 sm:p-6"
            @click="toggleFaq(index)"
          >
            <span class="flex text-lg font-semibold text-black">
              {{ faq.question }}
            </span>
            <svg
              :class="{'rotate-180': faq.open}"
              class="w-6 h-6 text-gray-400 transition-transform duration-200"
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M19 9l-7 7-7-7"
              />
            </svg>
          </button>
          <transition name="faq" @before-enter="beforeEnter" @enter="enter" @leave="leave">
            <div
              v-show="faq.open"
              ref="faqContent"
              class="overflow-hidden transition-all duration-500 ease-in-out"
            >
              <div class="px-4 pb-5 sm:px-6 sm:pb-6">
                <p>
                  {{ faq.answer }} <a href="#" title="" class="text-blue-600 transition-all duration-200 hover:underline"></a>
                </p>
              </div>
            </div>
          </transition>
        </div>
      </div>

      <p class="text-center text-gray-600 textbase mt-9">
        Tem mais alguma dúvida?
        <a href="https://api.whatsapp.com/send/?phone=5521983192355&text=Olá,%20gostaria%20de%20simular%20meu%20saldo%20FGTS!" title="" class="font-medium text-blue-600 transition-all duration-200 hover:text-blue-700 focus:text-blue-700 hover:underline">
          Fale conosco
        </a>
      </p>
    </div>
  </section>
</template>

<script>
export default {
data() {
  return {
    faqs: [
      {
        question: "Quais são os requisitos para antecipar meu FGTS?",
        answer: "Você precisa ter saldo ativo ou inativo na conta do FGTS, ser maior de idade ou emancipado e estar na modalidade de saque-aniversário do FGTS. Para mudar a modalidade, basta acessar o aplicativo e solicitar a alteração.",
        open: false,
      },
      {
        question: "Qual a taxa de juros aplicada?",
        answer: "A taxa de juros pode chegar a 1,80% ao mês, mas pode ser menor dependendo da análise.",
        open: false,
      },
      {
        question: "É necessário passar por avaliação de crédito?",
        answer: "Não, a operação é 100% pré-aprovada para quem possui saldo mínimo de R$ 150,00 no FGTS.",
        open: false,
      },
      {
        question: "Em qual banco posso receber o crédito?",
        answer: "O valor pode ser depositado em qualquer conta bancária, exceto contas-salário. Durante a simulação do empréstimo com nossos consultores, você informará a conta desejada para o recebimento.",
        open: false,
      },
      {
        question: "Como funciona o pagamento das parcelas?",
        answer: "Não há boletos, pois os juros serão descontados diretamente do seu saldo do FGTS, evitando assim pagamentos mensais que possam impactar sua renda.",
        open: false,
      },
    ],
  };
},
methods: {
  toggleFaq(index) {
    this.faqs[index].open = !this.faqs[index].open;
  },
  beforeEnter(el) {
    el.style.maxHeight = 0;
  },
  enter(el) {
    el.style.maxHeight = el.scrollHeight + 'px';
  },
  leave(el) {
    el.style.maxHeight = 0;
  }
},
};
</script>

<style scoped>
@import "tailwindcss/base";
@import "tailwindcss/components";
@import "tailwindcss/utilities";

.transition-max-height {
transition: max-height 0.5s ease-in-out;
}
</style>