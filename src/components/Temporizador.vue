<template>
    <div class="is-flex is-align-items-center is-justify-content-space-between">
        <Cronometro :tempoEmSegundos="tempoEmSegundos"/>
        <Botao :funcao="iniciar" :desabilitado="cronometroRodando" icone="fas fa-play" texto="play"/>
        <Botao :funcao="finalizar" :desabilitado="!cronometroRodando" icone="fas fa-stop" texto="stop"/>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Cronometro from './Cronometro.vue';
import Botao from './Botao.vue';

export default defineComponent({
    name: 'TemporizadorTarefa',
    emits: ['aoTemporizadorFinalizado'],
    data() {
        return {
            tempoEmSegundos: 0,
            cronometro: 0,
            cronometroRodando: false
        }
    },
    components:{
        Cronometro, Botao
    },
    methods: {
        iniciar() {
            this.cronometroRodando = true;
            this.cronometro = setInterval(() =>{
                this.tempoEmSegundos++;
            },1000)
        },
        finalizar () {
            this.cronometroRodando = false;
            clearInterval(this.cronometro);
            this.$emit('aoTemporizadorFinalizado',this.tempoEmSegundos);
            this.tempoEmSegundos = 0;
        }
    }
})

</script>
