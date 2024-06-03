<template>

  <section class="src-components-formulario">

    <input type="text" 
           id="input" 
           placeholder="Ingrese un texto aqui" 
           v-model.trim="textoInput">
    <br>
    <br>

    <p v-if="textoInput">Cantidad de Caracteres: {{ cantidadDeCaracteres }}</p>

    <p v-if="textoInput">1 - {{ codificarTexto(textoInput) }} (codificado)</p>
    <p v-if="textoInput">2 - {{ textoInput.toUpperCase() }} (mayuscula)</p>
    <p v-if="textoInput">3 - {{ textoInput.toLowerCase() }} (minuscula)</p>
    <p v-if="textoInput">4 - {{ formatearTextoMayMin(textoInput) }} (mayuscula / minuscula)</p>
    <p v-if="textoInput">5 - {{ formatearTextoMinMay(textoInput) }} (minuscula / mayuscula)</p>

    <hr>

    <p>Respuestas 1: C -- 2:C -- 3: A</p>
  </section>

</template>

<script lang="js">

  export default  {
    name: 'src-components-formulario',
    props: [],
    mounted () {

    },
    data () {
      return {
        textoInput:null
      }
    },
    methods: {

      codificarTexto(texto){
        let arrTexto = texto.toLowerCase().split('');
        for(let i = 0; i < arrTexto.length; i++){
          
          switch(arrTexto[i]){
            case 'a':
              arrTexto[i]= 'u';
              break
            case 'e':
              arrTexto[i] = 'o';
              break
            case 'o':
              arrTexto[i] = 'e';
              break
            case 'u':
              arrTexto[i] = 'a';
              break
          }
        }
        return arrTexto.join('');
      },

      formatearTextoMayMin(texto){
        let arrTexto = texto.toLowerCase().split('');
        for(let i = 0; i < arrTexto.length; i++){
          if(i % 2 == 0){
            arrTexto[i] = arrTexto[i].toUpperCase();
          }
        }
        return arrTexto.join('');
      },

      formatearTextoMinMay(texto){
        let arrTexto = texto.toUpperCase().split('');
        for(let i = 0; i < arrTexto.length; i++){
          if(i % 2 == 0){
            arrTexto[i] = arrTexto[i].toLowerCase();
          }
        }
        return arrTexto.join('');
      }

    },
    computed: {

      cantidadDeCaracteres() {
       return this.textoInput ? this.textoInput.length : 0;
      }

    }
}


</script>

<style scoped lang="css">
p {
  font-size: 17px;
  font-weight:500;
}
</style>