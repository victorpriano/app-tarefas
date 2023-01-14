<template>
    <div>
        <input class="form-control" type="text" v-model="descricao" placeholder="Informe uma descrição" />
        <button class="btn btn-light" @click="salvar">Criar</button>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
    /* eslint-disable */
    name: 'Formulario',
    emits: ['aoSalvarTarefa'],
    data() {
        return {
            descricao: ''
        }
    },
    methods: {
        salvar() : void {
            this.$emit('aoSalvarTarefa', {
                descricao: this.descricao
            })
        }
    }

})
</script>

<style scoped>

</style>
