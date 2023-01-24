<template>
  <box>
    <div class="columns">
      <div class="column is-7">
        {{ tarefa.descricao || 'Tarefa sem descrição' }}
      </div>
      <div class="column">
        <Cronometro :tempoEmSegundos="tarefa.duracaoEmSegundos" />
      </div>
    </div>
  </box>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue'
import Cronometro from './Cronometro.vue'
import ITarefa from '../Interfaces/ITarefa'
import box from './box.vue'


export default defineComponent({
  name: 'Tarefa-tracker',
  components: {
    Cronometro,
    box
  },
  props: {
    tarefa: {
      type: Object as PropType<ITarefa>,
      required: true
    }
  },
})
</script>

<style scoped>
.box {
  background: #FAF0CA;
}
</style>