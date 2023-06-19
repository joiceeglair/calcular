<script setup>
  import { reactive } from 'vue';
  import Cabecalho from './components/Cabecalho.vue'
  import Operacao from './components/Operacao.vue'
  import Resultado from './components/Resultado.vue'

  const estado = reactive({
    operation: '+',
    num1: '',
    num2: ''
  })

  const resultado = () => {
    const {operation} = estado
    if (operation === '-') {
      return parseFloat(estado.num1) - parseFloat(estado.num2)
    } else if (operation === '*'){
      return parseFloat(estado.num1) * parseFloat(estado.num2)
    } else if (operation === '/'){
      return parseFloat(estado.num1) / parseFloat(estado.num2)
    } else {
      return parseFloat(estado.num1) + parseFloat(estado.num2)
    }
  }

</script>

<template>

  <body>
    <div class="container">
      <Cabecalho />
      <Operacao :operacao="evento => estado.operation = evento.target.value" 
        :num1="evento => estado.num1 = evento.target.value"
        :num2="evento => estado.num2 = evento.target.value"/>
      <Resultado :num1="estado.num1" :num2="estado.num2" :result="resultado()"/>
    </div>
  </body>

</template>

<style scoped>

  *{
    margin: 0;
    padding: 0;
  }

  .container {
    font-family: 'Orbitron', sans-serif;
    margin: 0 auto;
    text-align: center;
    background-color: rgb(158, 156, 156);
  }

</style>