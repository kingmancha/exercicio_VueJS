<template>
  <div class="container">
    <Cabecalho />
    <Formulario
      :numero1="estado.numero1"
      :numero2="estado.numero2"
      :operacao="estado.operacao"
      @update:numero1="estado.numero1 = $event"
      @update:numero2="estado.numero2 = $event"
      @update:operacao="estado.operacao = $event"
    />
    <Resultado
      :numero1="estado.numero1"
      :numero2="estado.numero2"
      :operacao="estado.operacao"
    />
  </div>
</template>

<script setup>
import { reactive } from 'vue';
import Cabecalho from './components/Cabecalho.vue';
import Formulario from './components/Formulario.vue';
import Resultado from './components/Resultado.vue';

const estado = reactive({
  numero1: 0,
  numero2: 0,
  operacao: 'add',
});
</script>

<style scoped>
.container {
  max-width: 600px;
  margin: auto;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 4px;
  text-align: center;
}
</style>
