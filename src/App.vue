<template>
  <main>
      <div>
        <div class="formulario">
          <Formulario @aoSalvarTarefa="salvarTarefa" />
        </div>
        <div class="box-tarefas">
          <div class="tarefas">
            <p v-if="listaVazia" class="texto-tarefas">Nenhuma tarefa até o momento...</p>
            <Tarefa v-for="(tarefa, index) in tarefas" :key="index" :tarefa="tarefa" />
          </div>
        </div>
      </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

import Formulario from '@/components/Formulario.vue'
import Tarefa from '@/components/Tarefa.vue'

import { ITarefa } from './interfaces/ITarefa';

export default defineComponent({
  name: 'App',
  components: {
    Formulario,
    Tarefa
  },
  data() {
    return {
      tarefas: [] as ITarefa[]
    }
  },
  methods: {
    salvarTarefa(tarefa: ITarefa){
      this.tarefas.push(tarefa)
    }
  },
  computed: {
    listaVazia(): boolean {
      return this.tarefas.length === 0
    }
  }
});
</script>

<style>
  main {
    max-width: 100%;
    height: 100vh;
    background: #c2d8b9;
    padding-top: 30px;
    display: flex;
    justify-content: center;
    align-content: center;
    flex-direction: row;
  }

  .box-tarefas {
    width: 500px;
    height: 484px;
    margin-top: 10px; 
    background-color: #e4f0d0;
    padding: 10px;
    border-radius: 2px;
    overflow: auto;
  }

  .tarefas {
    margin-top: 10px;
  }

  .texto-tarefas {
    text-align: center;
  }

  ::-webkit-scrollbar-track {
    background-color: #F4F4F4;
  }
  
  ::-webkit-scrollbar {
      width: 6px;
      background: #F4F4F4;
  }

  ::-webkit-scrollbar-thumb {
      background: #dad7d7;
  }
</style>
