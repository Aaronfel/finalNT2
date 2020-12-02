<template>

  <section class="src-components-texto">
    <h1>input color</h1>
    <input type="text"
      id="color"
      class="form-control"
      v-model="color"
    >
    <h1>input color colorFondo</h1>
    <input type="text"
      id="colorFondo"
      class="form-control"
      v-model="colorFondo"
    >
    <h1>imput del tamaño</h1>
    <input type="text"
      id="tamaño"
      class="form-control"
      v-model="tamanio"
    >
    <hr>
    <h2>input a editar</h2>
    <input type="text"
    class="form-control"
    :style="{'font-size': getTamanio(), 'color': getColor(), 'background-color': getColorFondo() }"
    v-model="texto"
    >
    <div v-if="texto">
    {{'la cantidad de palabras es de: ' + cantidadPalabras}}
    </div>
      <h3>Tablachoice</h3>
       
      <h1>Multiple Choice</h1>
      <hr>
      
      <div class="table-responsive">
        <table class="table">
          <tr class="bg-success text-white">
            <th>Pregunta</th>
            <th>Respuestas</th>
          </tr>
          <tr class="bg-secondary text-white" v-for="(preg, index) in preguntas" :key="index">
            <td>{{ preg.pregunta }}</td>
            <td>{{ preg.respuestas }}</td>
          </tr>
        </table>
      </div>
  </section>

</template>

<script>

  export default  {
    name: 'src-components-texto',
    props: [],
    mounted () {

    },
    data () {
      return {
        tamanio: '',
        color: '',
        colorFondo: '',
        texto: '',

         preguntas: [
          {pregunta: 1, respuestas:['b']}
          ,{pregunta: 2, respuestas:['c']}
          ,{pregunta: 3, respuestas:['b']}
          ,{pregunta: 4, respuestas:['c']}
          ,{pregunta: 5, respuestas:['d']}
        ]
      }
    },
    methods: {
      getColor(){
        return this.color
      },
      getColorFondo() {
        return this.colorFondo
      },
      getTamanio() {
        return this.getTamanio
      }
    },
    computed: {
        cantidadPalabras(){
          return this.texto.split(' ').length
        }
    }
}


</script>

<style scoped lang="css">
  .src-components-texto {

  }
</style>
