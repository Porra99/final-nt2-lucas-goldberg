<template>

  <section class="src-components-codificacion">
    <input type="text" v-model="valor">
    <br>
    <br>
    <b>Cantidad de letras: </b> {{ amount }}
    <br>
    <br>
    <b>Codificado: </b> {{ valor | codificar }}
    <br>
    <br>
    <b>Mayusculas: </b>{{ valor.toUpperCase() }}
    <br>
    <br>
    <b>Minusculas: </b>{{ valor.toLowerCase() }}
    <br>
    <br>
    <b>Intercalado primera Mayuscula: </b>{{ valor | intercalarMay }}
    <br>
    <br>
    <b>Intercalado primera Minuscula: </b>{{ valor | intercalarMin }}
    <br>
    <br>
    
    <p><b>1:B 2:B 3:C 4:B 5:B</b></p>

  </section>

</template>

<script lang="js">

  export default  {
    name: 'src-components-codificacion',
    props: [],
    mounted () {

    },
    data () {
      return {
        valor: ''
      }
    },
    methods: {

    },
    computed: {
      amount(){
        return this.valor.length
      }
    },

    filters: {
      codificar(valor) {
        const letras = valor.split('')
        const letrasCodif = []

        letras.forEach(letra => {
          switch (letra) {
            case 'a':
              letra = 'u'
              break;
            case 'A':
              letra = 'U'
              break;
            case 'e':
              letra = 'o'
              break;
            case 'E':
              letra = 'O'
              break;
            case 'o':
              letra = 'e'
              break;
            case 'O':
              letra = 'E'
              break;
            case 'u':
              letra = 'a'
              break;
            case 'U':
              letra = 'A'
              break;
            
          }
          letrasCodif.push(letra);
        });
        return letrasCodif.join('')
      },

      intercalarMay(valor){
        const letras = []
        for (let i = 0; i < valor.length; i++) {
          if(i % 2 == 0) {
            letras.push(valor[i].toUpperCase())
          }
          if(i % 2 != 0){
            letras.push(valor[i].toLowerCase())
          }
        }
        return letras.join('')
      },

      intercalarMin(valor){
        const letras = []
        for (let i = 0; i < valor.length; i++) {
          if(i % 2 != 0) {
            letras.push(valor[i].toUpperCase())
          }
          if(i % 2 == 0){
            letras.push(valor[i].toLowerCase())
          }
        }
        return letras.join('')
      }
    }
}


</script>

<style scoped lang="css">
  .src-components-codificacion {

  }
</style>
