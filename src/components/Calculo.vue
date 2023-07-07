<script setup>
const props = defineProps(["primeiroValor", "segundoValor", "operacao", "func"]);
</script>

<template>
  <section>
    <div class="row">
      <div class="col">
        <label for="val1">Primeiro valor: </label>
        <input @keyup="props.primeiroValor" type="number" name="val1" />
      </div>
      <div class="col">
        <label for="val2">Segundo valor: </label>
        <input @keyup="props.segundoValor" type="number" name="val2" />
      </div>
      <div class="col-md-3">
        <label for="val2">Operação </label>
        <select @change="props.operacao">
          <option value="escolha">Escolha a operação</option>
          <option value="somar">Somar</option>
          <option value="subtrair">Subtrair</option>
          <option value="multiplicar">Multiplicar</option>
          <option value="dividir">Dividir</option>
        </select>
      </div>
    </div>
    <h2 class="text-center mt-3">Resultado: {{ props.func }}</h2>
  </section>
</template>

<style scoped>
input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}
</style>
