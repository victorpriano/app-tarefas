<template>
  <main>
    <div class="box">
      <div class="title">
        <h1>Tarefas</h1>
      </div>

      <div class="formulario">
        <Formulario @aoSalvarTarefa="salvarTarefa" />
      </div>

      <div class="tarefas">
        <Tarefa v-for="(tarefa, index) in tarefas" :key="index" :tarefa="tarefa" />
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
  }
});
</script>

<style>
  main {
    width: 96vw;
    height: 80vh;
    display: flex;
    background: #c2d8b9;
    align-items: center;
    flex-direction: row;
    justify-content: center;
  }
  .box {
    background-color: #e4f0d0;
    width: 300px;
    height: 300px;
    padding: 20px;
    border-radius: 2px;
  }
</style>
