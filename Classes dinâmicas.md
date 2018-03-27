# curso-vuejs-udemy
Lembrete de algumas informações importante de curso.

1 - Exemplo de classes dinâmicas:

@click="attatchRed = !attatchRed"
:class="{red: attatchRed}"

@click="attatchRed = !attatchRed"
:class="{red: attatchRed, blue = !attatchRed }"

@click="attatchRed = !attatchRed"
:class="divClasses"
  computed: {
    divClasses() {
      return {
        red: this.attachRed,
        blue: !this.attachRed,
      };
    }
  }
// - Também é possivel setar a classe até por input e também aceita um array de classes como exemplo.
.demo(
@click="attachRed = !attachRed"
:class="color")
input(type="text" v-model="[]")
  data: () => ({
    color: 'green',
  }),
