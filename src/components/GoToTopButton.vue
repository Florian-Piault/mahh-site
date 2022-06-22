<script setup>
import Icon from "./Icon.vue";
const goTop = () => {
  window.scrollTo(0, 0);
};
</script>

<template>
  <button class="btn btn-primary btn-round sticky" @click="goTop">
    <Icon icon="arrow-up" />
  </button>
</template>

<style scoped>
.sticky {
  position: fixed;
  bottom: 0;
  right: 0;
  margin: 0.5rem;
  z-index: 100;
}
.btn-round {
  border-radius: 50%;
}
</style>
