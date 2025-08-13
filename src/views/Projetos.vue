<template>
    <div class="projetos">
        <h1 class="title">Projetos</h1>
    </div>
    <routerView></routerView>
</template>

<script lang="ts">
import { defineComponent } from 'vue';


export default defineComponent({
    name:'ProjetosTarefas'
})

</script>

<style scoped>
.projetos {
    padding: 1.25rem;
}
</style>