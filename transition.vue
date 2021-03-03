<template>
  <div>
    <button @click="ativo = !ativo">Ativar</button>

    <transition appear name="fade" @enter="enter">
      <h1>Serviços</h1>
    </transition>
  </div>
</template>

<script>
export default {
  data() {
    return {
      ativo: false,
    };
  },
  methods: {
    enter() {},
  },
};
</script>

<style>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 2s;
}

.animar {
  transition: opacity 2s;
}

.fade-enter,
.fade-leave-to {
  opacity: 0;
}
</style>
