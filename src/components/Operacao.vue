<script setup>
  const props = defineProps(['operacao', 'num1', 'num2'])
</script>

<template>
  <div class="operation">
    <h2>Selecione e operação para o resultado</h2>
  </div>
  <div>
    <input class="no-spin" @keyup="props.num1" required type="number" placeholder="Digite o N."/>

    <select @change="props.operacao">
      <option value="+">+</option>
      <option value="-">-</option>
      <option value="*">*</option>
      <option value="/">/</option>
    </select>
    
    <input class="no-spin" @keyup="props.num2" required type="number" placeholder="Digite o N."/>
  </div>

</template>

<style>
  input {
    margin: 30px;
    padding: 4px;
    border-radius: 4px;
  }

  .no-spin::-webkit-inner-spin-button,
  .no-spin::-webkit-outer-spin-button {
  -webkit-appearance: none;
  margin: 0;
  }

</style>