<template>
    <div class="resultado">
        <p>Resultado: {{ resultado }}</p>
    </div>
</template>

<script setup>
import { computed } from 'vue';
import { defineProps } from 'vue';

const props = defineProps({
    numero1: Number,
    numero2: Number,
    operacao: String,
});

const resultado = computed(() => {
    switch (props.operacao) {
        case 'add':
            return props.numero1 + props.numero2;
        case 'subtract':
            return props.numero1 - props.numero2;
        case 'multiply':
            return props.numero1 * props.numero2;
        case 'divide':
            return props.numero2 !== 0 ? props.numero1 / props.numero2 : 'Divisão por zero!';
        default:
            return 0;
    }
});
</script>

<style