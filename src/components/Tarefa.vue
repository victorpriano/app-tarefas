<template>
    <div>
        <ul>
            <li>{{ tarefa.descricao }}</li>
        </ul>
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
