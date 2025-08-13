<template>
    <button class="button" @click="funcao" :disabled="desabilitado">
        <span class="icon">
            <i :class="icone"></i>
        </span>
        <span>{{texto}}</span>
    </button>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { PropType } from 'vue';
export default defineComponent({
    name: 'BotaoTemporizador',
    props: {
        funcao: {
            type: Function as PropType<() => void>,
            required: true
        },
        desabilitado: {type: Boolean},
        icone: {type: String},
        texto: {type: String}
    },
})
</script>