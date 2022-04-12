
<template>
  <div class="jogo">
     <Forca :erros = "erros"></Forca>

     <Palavra :palavra = "palavra"
     :dica = "dica"
     :verificarLetra = "verificarLetra"
     :etapa = "etapa"></Palavra>

     <Teclado
     :letras = "letras"
     :verificarLetra = "verificarLetra"
     :jogar = "jogar"
     ></Teclado>
  </div>
</template>

<script>
import Forca from './Forca.vue';
import Palavra from './Palavra.vue';
import Teclado from './Teclado.vue';


export default {
  name: 'Jogoraiz',
  props:{
    erros: Number,
    palavra: String,
    dica: String,
    verificarLetra: Function,
    etapa: String,
    letras: Array,
    jogar:Function
  },
  data() {
      return {
         
      }
  },
  methods: {
     
      
  },
  components:{
    Forca,
    Palavra,
    Teclado
  }
  
}
</script>

<style>
  .jogo{
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
  }

</style>