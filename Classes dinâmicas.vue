<template lang="pug">
#app
  div
    h3 Exercicio 1 )
    | Start the Effect with the Button. The Effect should
    | alternate the "highlight" or "shrink" class on each new setInterval tick
    |(attach respective class to the div with id "effect" below)
  button(@click="piscaPisca") Botão AQUI
    div#effect(:class="highlightOrShrink")
  h3 Exercicio 2
  | Create a couple of CSS classes and attach them via the array syntax
  .pegaClasse(:style="[estilera, {height: width + 'px'}]" ) I got class :)
  input(type="text" v-model="color")
  input(type="text" v-model="width")
  h3 Exercicio 3
  | Let the user enter a class (create some example classes) and attach it
  div
    input(type="text" v-model="classeCustom")
    div#effect(:class="[classeCustom]") Exemplos: highlight, primeira e shrink
  //- <!-- 4) -->
  div
    h3 Exercicio 4
    | Let the user enter a class and enter true/ false for another
    |  class (create some example classes) and attach the classes
  input(type="text" v-model="classeCustom")
  input(type="text" v-model="inVisivel")
  div(v-bind:class="[{visivel: inVisivel}, classeCustom]")
  div
  h3 Exercicio 5
  | Repeat 3) but now with values for styles (instead of class names)
  |. Attach the respective styles.
  input(type="text" v-model="estiloUm.backgroundColor")
  div#effect(:style="[estiloUm]" )
  //- <!-- 6)
  //-  -->
  h3 Exercicio 6
  | Create a simple progress bar with setInterval and style bindings
  | . Start it by hitting the below button.
  div(v-bind:class="['barraProgresso']" v-bind:style='barraCarregar')
  button(v-on:click="carregar") Start Progress
</template>

<script>
export default {
  data: () => ({
    highlightOrShrink: {
      highlight: false,
      shrink: true,
    },
    barraCarregar: {
      width: '0',
      height: '50px'
    },
    float: 'float',
      inVisivel: true,
      estiloUm: {
        width: '100px',
        height: '150px',
        backgroundColor: 'gray'
      },
    color: 'green',
    width: 100,
    classeCustom: '',
  }),
  computed: {
    estilera() {
      return {
        backgroundColor: this.color,
        width: this.width + 'px'
      };
    },
  },
  methods: {
    piscaPisca() {
    var vm = this;
      setInterval(function() {
        vm.highlightOrShrink.highlight = !vm.highlightOrShrink.highlight;
        vm.highlightOrShrink.shrink = !vm.highlightOrShrink.shrink;
      }, 5000);
    },
    carregar() {
      var vm = this;
      var width = 0;
      setInterval(function() {
        width = width +1;
        vm.barraCarregar.width = width + 'px';
      }, 10);
    }
  },
};
</script>

<style>
input[type=text] {
  border: 2px solid blue;
  border-radius: 4px;
}
#effect {
  width: 100px;
  height: 100px;
  border: 1px solid black;
}

.highlight {
  background-color: red;
  width: 200px !important;
}

.shrink {
  background-color: gray;
  width: 50px !important;
}
.primeira {
  background-color: lightblue;
  border: 1px solid black;
}
.visivel {
  width: 100px;
  height: 50px;
}
.float {
  float: right;
}
.barraProgresso {
  width: 700px;
  height:50px;
  border: 1px solid black;
}
</style>
