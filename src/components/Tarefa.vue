<template>
    <div class="tarefa">
        <div>
            <div class="descricaoTarefa">
                {{ tarefa.descricao }}
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import { ITarefa } from '@/interfaces/ITarefa'
import { defineComponent, PropType } from 'vue'

export default defineComponent({
    /* eslint-disable */
    name: 'Tarefa',
    props: {
        tarefa: {
            type: Object as PropType<ITarefa>,
            required: true
        }
    }
})
</script>

<style scoped>
    .tarefa {
        width: 480px;
        margin-bottom: 10px;
        background-color: #c2d8b9;
        padding: 12px;
        border-radius: 5px;
    }
</style>
