<script>
import TheHeader from "../components/Global/TheHeader.vue";
import footers from "../components/Global/footers.vue";

export default {
  components: {
    TheHeader,
    footers,
  },
}
</script>

<template>

<TheHeader />
<h1>Política de Privacidade da Star Consignados</h1>
<div class="container">
    <p>Última atualização: [28/03/25]</p>
    <h2>1. Introdução</h2>
    <p>Agradecemos por escolher a Star Consignados. Sua privacidade e a proteção dos seus dados pessoais são fundamentais para nós. Esta Política de Privacidade explica como coletamos, utilizamos, compartilhamos e protegemos as informações obtidas através do uso dos nossos serviços financeiros.</p>
    
    <h2>2. Informações Coletadas</h2>
    <p>Coletamos informações necessárias para o fornecimento dos nossos serviços, incluindo:</p>
    <ul>
        <li>Dados de cadastro: nome, e-mail, telefone.</li>
        <li>Dados de uso do serviço: logs de atividades e estatísticas de uso.</li>
        <li>Informações de pagamento, caso aplicável.</li>
    </ul>
    
    <h2>3. Uso das Informações</h2>
    <p>Utilizamos as informações coletadas para:</p>
    <ul>
        <li>Prover, operar e manter os serviços da Star Consignados.</li>
        <li>Melhorar, personalizar e expandir nossos serviços financeiros.</li>
        <li>Desenvolver novos produtos, serviços e funcionalidades.</li>
        <li>Comunicar com você, diretamente ou através de um dos nossos parceiros, incluindo para atendimento ao cliente, para fornecer atualizações e outras informações relacionadas ao serviço, e para fins de marketing e promoção.</li>
        <li>Enviar e-mails e outras formas de comunicação que você consentiu em receber.</li>
    </ul>
    
    <h2>4. Compartilhamento de Informações</h2>
    <p>Não vendemos nem alugamos suas informações pessoais a terceiros. As informações podem ser compartilhadas com terceiros nas seguintes situações:</p>
    <ul>
        <li>Fornecedores de serviços e parceiros que nos ajudam a operar os serviços.</li>
        <li>Requisições legais, quando acreditamos de boa-fé que somos obrigados a fazê-lo sob a lei aplicável.</li>
    </ul>
    
    <h2>5. Segurança das Informações</h2>
    <p>Empregamos medidas de segurança significativas para proteger contra o acesso não autorizado ou ilegal, alteração, divulgação ou destruição das informações que coletamos e armazenamos.</p>
    
    <h2>6. Alterações na Política de Privacidade</h2>
    <p>Podemos atualizar nossa Política de Privacidade periodicamente. Avisaremos você sobre quaisquer mudanças publicando a nova Política de Privacidade nesta página.</p>
    
    <h2>7. Contato</h2>
    <p>Se tiver perguntas sobre esta Política de Privacidade, entre em contato conosco através do e-mail <strong>contato@starconsignados.com.br</strong> ou pelo telefone <strong>(21) 983192355</strong>.</p>
</div>

<footers />

</template>

<style scoped>

.container {
    width: 70%;
        margin: 0 auto;
        background: white;
        padding: 20px;
        text-align: left;
    }
    h1, h2 {
        color: #333;
    }
    p, ul {
        margin: 20px 0;
    }
    li {
        margin-bottom: 10px;
    }

    h1 {
        text-align: center;
        padding-top: 20px;
        font-size: 32px;
        font-weight: 700;
    }

    h2 {
        font-size: 22px;
        padding-bottom: 10px;
    }

    @media (max-width: 500px) {
        .container {
            width: 90%;
        }
        h1 {
            font-size: 24px;
        }
        h2 {
            font-size: 20px;
        }
    }

</style>
