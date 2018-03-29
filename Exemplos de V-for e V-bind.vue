<template lang="pug">
div
  ul
    //-  Usando o v-bind ":key" eu consigo  fazer que o vueJS interprete a 
    //- entrada de forma diferente, não substituindo a entrada apenas, mas salvando a lista.
    li(color="success" v-for="(ingrediente, i) in ingredientes" :key='ingrediente')  {{ ingrediente }} ({{ i }})
    li(v-for="(pessoa, i) in pessoas")
      div(v-for="(valor, key, index) in pessoa") > {{ key }}:  {{ valor }} / - {{ index }}
  div
    v-btn(@click="ingredientes.push('beterraba')") Colocar beterraba
    ul
      span(v-for="n in 10") {{ n }}
</template>
<script>
export default {
  data: () => ({
    ingredientes: [
      'carne',
      'fruta',
      'bolachas',
    ],
    pessoas: [
      {
        nome: 'Percival',
        idade: 56,
        cor: 'preto',
      },
      {
        nome: 'Rebosteio',
        idade: 65,
        cor: 'azul',
      },
      {
        nome: 'Josefa',
        idade: 22,
        cor: 'amarelo',
      },
    ],
  }),
};
</script>

<style lang="css">
</style>
