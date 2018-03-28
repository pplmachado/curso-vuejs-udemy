<template lang="pug">
div
  p(v-if="show") Teste 1
    p(v-else) Substituto do Teste 1
  p Teste 2
  //-  A diferença do v-if para o v-show é que no segundo ele esconde
  //- o elemento e no v-if ele não chega nem a ser renderizado, como se fosse deletado da aplicação.
  template(v-show="show")
    | Dentro do template
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

<style lang="css">
</style>
