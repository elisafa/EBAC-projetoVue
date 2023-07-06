<script setup>
import { reactive } from "vue";

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
    <header class="p-5 mb-4 mt-4 bg-light rounded-4">
      <h1 class="text-center">Calculadora Vue</h1>
      <p class="text-center">Calculadora da EBAC com VueJS</p>
    </header>
    <section>
      <div class="row">
        <div class="col">
          <label for="val1">Primeiro valor: </label>
          <input
            @keyup="(evento) => (estado.primeiroValor = evento.target.value)"
            type="number"
            name="val1"
          />
        </div>
        <div class="col">
          <label for="val2">Segundo valor: </label>
          <input
            @keyup="(evento) => (estado.segundoValor = evento.target.value)"
            type="number"
            name="val2"
          />
        </div>
        <div class="col-md-3">
          <label for="val2">Operação </label>
          <select @change="(evento) => (estado.operacao = evento.target.value)">
            <option value="escolha">Escolha a operação</option>
            <option value="somar">Somar</option>
            <option value="subtrair">Subtrair</option>
            <option value="multiplicar">Multiplicar</option>
            <option value="dividir">Dividir</option>
          </select>
        </div>
      </div>
      <h2 class="text-center mt-3">Resultado: {{ operacao() }}</h2>
    </section>
  </div>
</template>

<style scoped></style>
