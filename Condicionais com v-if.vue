<template lang="pug">
div
  p(v-if="show") Teste 1
    p(v-else) Substituto do Teste 1
  p Teste 2
  v-btn(@click="show = !show" dark ) Remover o teste 1
</template>

<script>
export default {
  data() {
    return {
      show: true,
    };
  },
};
</script>
