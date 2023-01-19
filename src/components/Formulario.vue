<template>
    <div class="bloco-form">
        <div class="titulo">
            <h1>Minhas Tarefas</h1>
        </div>
        <div class="formulario">
            <input class="form-control" id="form" type="text" v-model="descricao" placeholder="Informe uma descrição" />
        </div>
        <button class="botao btn btn-light" @click="salvar">Criar</button>
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
            this.descricao = ''
        }
    }

})
</script>

<style scoped>

    .titulo {
        text-align: center;
    }
    .formulario {
        display: inline-block
    }

    .formulario input {
        width: 428px;
        margin-left: 3px;
    }

    .botao {
        margin-bottom:3px;
        margin-left: 5px;
    }

</style>
