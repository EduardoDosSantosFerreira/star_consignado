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
<h1>Termos de Uso da Star Consignados</h1>
<div class="container">
    <p>Última atualização: [28/04/25]</p>
    <p>Bem-vindo à Star Consignados!</p>
    <p>Agradecemos por escolher nossos serviços financeiros. Ao utilizar a Star Consignados, você concorda em estar vinculado a estes Termos de Uso.</p>
    
    <h2>1. Descrição do Serviço</h2>
    <p>A Star Consignados oferece soluções de crédito acessíveis e sem complicação, conectando você a um crédito justo. Nossos serviços incluem antecipação do saque aniversário do FGTS e crédito para aposentados e pensionistas do INSS.</p>
    
    <h2>2. Privacidade e Proteção de Dados Pessoais</h2>
    <p>Em conformidade com a Lei Geral de Proteção de Dados (LGPD), valorizamos a privacidade e a segurança dos seus dados pessoais, incluindo:</p>
    <ul>
        <li>Proteger suas informações pessoais, como dados de contato e informações financeiras.</li>
        <li>Não compartilhar suas informações com terceiros, exceto quando necessário para a prestação do serviço ou exigido por lei.</li>
        <li>Implementar medidas de segurança para proteger seus dados contra acessos não autorizados.</li>
    </ul>
    
    <h2>3. Condições de Uso</h2>
    <p>Ao utilizar os serviços da Star Consignados, você concorda em:</p>
    <ul>
        <li>Não utilizar os serviços para fins ilícitos ou para transmitir conteúdo que viole leis aplicáveis.</li>
        <li>Manter a confidencialidade de suas credenciais de acesso.</li>
        <li>Assumir total responsabilidade pelas atividades realizadas sob sua conta.</li>
    </ul>
    
    <h2>4. Limitação de Responsabilidade</h2>
    <p>Os serviços da Star Consignados são fornecidos na modalidade "como estão". Embora nos esforcemos para manter a qualidade e a disponibilidade, não garantimos que os serviços estarão livres de interrupções ou erros.</p>
    
    <h2>5. Modificações nos Termos</h2>
    <p>Reservamo-nos o direito de modificar estes Termos de Uso a qualquer momento. As alterações entram em vigor imediatamente após sua publicação em nosso site. Recomendamos a revisão periódica deste documento.</p>
    
    <h2>6. Contato</h2>
    <p>Para dúvidas ou suporte, entre em contato conosco através do e-mail <strong>contato@starconsignados.com.br</strong> ou pelo telefone <strong>(21) 983192355</strong>.</p>
    
    <p>Ao utilizar os serviços da Star Consignados, você confirma que compreendeu e concordou com estes Termos de Uso.</p>
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
p {
    margin: 20px 0;
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
