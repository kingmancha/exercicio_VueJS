<template>
    <div class="formulario">
        <input type="number" :value="numero1" @input="updateNumero1($event)" placeholder="Número 1" />
        <select :value="operacao" @change="updateOperacao($event)">
            <option value="add">+</option>
            <option value="subtract">-</option>
            <option value="multiply">*</option>
            <option value="divide">/</option>
        </select>
        <input type="number" :value="numero2" @input="updateNumero2($event)" placeholder="Número 2" />
    </div>
</template>

<script setup>
import { defineProps, defineEmits } from 'vue';

const props = defineProps({
    numero1: Number,
    numero2: Number,
    operacao: String,
});

const emit = defineEmits(['update:numero1', 'update:numero2', 'update:operacao']);

const updateNumero1 = (evento) => emit('update:numero1', evento.target.valueAsNumber);
const updateNumero2 = (evento) => emit('update:numero2', evento.target.valueAsNumber);
const updateOperacao = (evento) => emit('update:operacao', evento.target.value);
</script>

<style scoped>
.formulario {
    display: flex;
    justify-content: center;
    gap: 10px;
    margin-bottom: 20px;
}

input,
select {
    padding: 10px;
    font-size: 1em;
}
</style>