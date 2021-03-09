<template>
  <div>
    <ul>
      <li @click="componenteAtivo = 'PaginaSobre'">Sobre</li>
      <li @click="componenteAtivo = 'PaginaServicos'">Serviços</li>
    </ul>
    <component :is="componenteAtivo"></component>
    <transition mode="out-in"></transition>
  </div>
</template>

<script>
import PaginaSobre from "./PaginaSobre.vue";
import PaginaServicos from "./PaginaServicos.vue";

export default {
  components: {
    PaginaSobre,
    PaginaServicos,
  },
  data() {
    return {
      componenteAtivo: "PaginaSobre",
    };
  },
};
</script>

<style>
.v-enter-active {
  transition: all 0.3s;
}

.v-enter {
  opacity: 0;
  transform: translate3d(0, -20px, 0);
}
</style>
