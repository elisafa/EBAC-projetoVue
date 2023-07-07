<script setup>
import { reactive } from "vue";
import Cabecalho from "./components/Cabecalho.vue";
import Calculo from "./components/Calculo.vue";

const estado = reactive({
  operacao: "",
  primeiroValor: 0,
  segundoValor: 0,
});

const operacao = () => {
  const { operacao, primeiroValor, segundoValor } = estado;

  switch (operacao) {
    case "somar":
      const soma = Number(primeiroValor) + Number(segundoValor);
      return `${soma}`;
    case "subtrair":
      const subtrair = Number(primeiroValor - segundoValor);
      return `${subtrair}`;
    case "multiplicar":
      const multiplicar = Number(primeiroValor * segundoValor);
      return `${multiplicar}`;
    case "dividir":
      const dividir = Number(primeiroValor / segundoValor);
      return `${dividir}`;
    case "escolha":
      return `precisa escolher uma operação`;
    default:
      break;
  }
};
</script>

<template>
  <div class="container">
    <Cabecalho />
    <Calculo
      :primeiro-valor="(evento) => (estado.primeiroValor = evento.target.value)"
      :segundo-valor="(evento) => (estado.segundoValor = evento.target.value)"
      :operacao="(evento) => (estado.operacao = evento.target.value)"
      :func="operacao()"
    />
  </div>
</template>
