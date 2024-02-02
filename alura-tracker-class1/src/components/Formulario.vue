<template>
  <div class="box">
    <div class="columns">
      <div class="column is-8" role="form" aria-label="Formualrio para cricao de uma nova tarefas">
        <input type="text" class="input" placeholder="Qual tarefa voce desejar iniciar">
      </div>
      <div class="column">
        <div class="is-flex is-align-items-center is-justify-content-space-between">
          <section>
            <strong>
              {{ tempoDecorrido }}
            </strong>
          </section>
          <button class="button" @click="iniciar">
            <span class="icon">
              <i class="fas fa-play"></i>
            </span>
            <span>play</span>
          </button>
          <button class="button" @click="finalizar">
            <span class="icon">
              <i class="fas fa-stop"></i>
            </span>
            <span>stop</span>
          </button>
        </div>

      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'Formulario',
  data() {
    return {
      tempoEmSegundos: 0,
      cronometro: 0,
    }
  },
  computed: {
    tempoDecorrido(): string {
      return new Date(this.tempoEmSegundos * 1000).toISOString().substr(11, 8);
    }
  },
  methods: {
    iniciar() {
      //comecar a contagem
      // 1 seg = 1000ms
      this.cronometro = setInterval(() => {
        console.log('Incrementando...');
        this.tempoEmSegundos++;
        console.log(this.tempoEmSegundos);

      }, 1000);
    },
    finalizar() {
      console.log('finalizando');
      clearInterval(this.cronometro);
    }
  }
});
</script>

<style></style>