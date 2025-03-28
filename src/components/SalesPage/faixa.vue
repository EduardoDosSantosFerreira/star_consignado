<template>
    <section>
        <div class="large-container">
            <div class="flex flex-col lg:flex-row lg:items-center lg:justify-between">
                <div class="flex-1 flex items-center">
                    <div class="mt-3 sm:mt-0 sm:ml-4">
                        <h2 class="text-2xl font-semibold text-white">Digite seu saldo FGTS e simule agora mesmo:</h2>
                    </div>
                </div>

                <div class="form mt-6 w-full sm:max-w-md xl:max-w-lg xl:mt-0 lg:ml-8">
                    <div class="flex flex-col sm:flex-row items-center">
                        <input type="text" placeholder="R$" class="input-email" v-model="valor" required />
                        <div class="mt-2 sm:mt-6 sm:ml-2.5">
                            <button type="button" class="button-inscrever" @click="enviarWhatsApp">
                                Simular
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import { ref } from 'vue';

const valor = ref('');

const enviarWhatsApp = () => {
    const mensagem = `Olá, gostaria de simular meu FGTS com o valor de R$ ${valor.value}.`;
    const telefone = '5521983192355';
    const url = `https://api.whatsapp.com/send?phone=${telefone}&text=${encodeURIComponent(mensagem)}`;
    window.open(url, '_blank');
};
</script>

<style scoped>
section {
    background: rgb(99, 99, 99);
    padding: 10px;
}

.large-container {
    max-width: 80vw;
    margin: 0 auto;
    padding: 0 20px;
}

h2 {
    font-family: 'Poppins', sans-serif;
    font-size: 1.5rem;
    width: 100%;
    /* Ajustado para ocupar 100% em telas menores */
    margin-top: 10px;
    margin-left: 0;
    /* Removido o deslocamento negativo */
    font-weight: 600;
    color: #fff;
}

p {
    font-size: 3rem;
    margin-right: 1rem;
}

.input-email {
    width: 100%;
    /* Ajustado para ocupar 100% em telas menores */
    padding: 12px 16px;
    margin-top: 10px;
    font-size: 1rem;
    color: #1f2937;
    /* text-gray-900 */
    background-color: #ffffff;
    /* bg-white */
    border: 1px solid transparent;
    border-radius: 0.375rem;
    /* rounded-md */
    transition: border-color 0.2s, box-shadow 0.2s;
}

.input-email:focus {
    border-color: #d1d5db;
    /* border-gray-300 */
    box-shadow: 0 0 0 1px #274e8d;
    /* focus:ring-1 focus:ring-blue-500 */
    outline: none;
}

.button-inscrever {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    padding: 12px 40px;
    width: auto;
    /* Ajustado para auto em telas menores */
    margin-top: -10px;
    font-size: 1rem;
    font-weight: 700;
    color: rgb(0, 0, 0);
    background-color: #ffffff;
    /* bg-blue-500 */
    border: 1px solid transparent;
    border-radius: 0.375rem;
    /* rounded-md */
    transition: background-color 0.2s;
}

.button-inscrever:hover {
    background-color: #a5a5a5;
    color: rgb(255, 255, 255);
    /* hover:bg-blue-600 */
}

.button-inscrever:focus {
    outline: none;
    box-shadow: 0 0 0 2px #3b82f6;
    /* focus:ring-2 focus:ring-offset-2 focus:ring-blue-500 */
}

@media (max-width: 768px) {

    section {
        padding: 10px 0px;
    }

    h2 {
        padding-top: 10px;
        font-size: 1.4rem;
        /* Ajuste de tamanho para telas menores */
        width: 80vw;
        /* Garante que o título ocupe toda a largura */
        margin-bottom: -20px;
    }

    p {
        display: none;
    }

    .input-email {
        padding: 10px 10px;
        width: 70vw;
        /* Garante que o input ocupe toda a largura */
    }

    .button-inscrever {
        padding: 10px 10px;
        width: 70vw;
        /* Garante que o botão ocupe toda a largura */
        margin-top: 10px;
        margin-bottom: 30px;
    }
}
</style>
