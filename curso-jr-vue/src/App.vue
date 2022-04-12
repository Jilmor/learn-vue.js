<script setup>
import { RouterLink, RouterView } from 'vue-router'
import '../src/assets/base.css';
import Formulario from './components/Formulario.vue';
import Jogoraiz from './components/Jogoraiz.vue';
</script>

<template>
  <div id="app">

    <h1>Jogo da força Vue - Jr</h1>
    <section v-if="tela === 'inicio'" id="inicio">
      <Formulario v-if="etapa === 'palavra'"  title="Defina a Palavra" button="Proximo" :action = "setPalavra">

      </Formulario>
      <Formulario v-if="etapa === 'dica'"  title="Defina a Dica" button="Começar jogo" :action = "setDica">

      </Formulario>
    </section>
    <section v-if="tela === 'jogo'" id="jogo">
      <Jogoraiz :erros = "erros" 
      :palavra = "palavra"
      :dica = "dica"
      :verificarLetra= "verificarLetra"
      :etapa = "etapa"
      :letras = "letras"
      :Jogar= "jogar">
      </Jogoraiz>
    </section>
    

  </div>
</template>
<script> 

export default {
  name:'app',
  data() {
    return {
      tela:'inicio',
      etapa:'palavra',
      palavra:'',
      dica:'',
      erros: 0,
      letras:[]
    }
  },
  methods: {
    setPalavra: function(palavra){
      this.palavra = palavra;
      this.etapa = 'dica';
    },

    setDica: function(dica){
      this.dica = dica;
      this.etapa = 'jogo';
      this.tela='jogo';
    },

    verificarLetra:function(letra){
      return this.letras.find(item => item.toLowerCase() === letra.toLowerCase());
    },
    jogar:function(letra) {
      this.letras.push(letra);
      this.verificarErros(letra);
      
    },
    verificarErros:function(letra) {
if (this.palavra.toLowerCase().indexOf(letra.toLowerCase()) >= 0){
  return this.verificarAcertos();
}
    this.erros++;
    },
    verificarAcertos:function(letra) {

    }

  },
    
  components: {
    Formulario,
    Jogoraiz
  }
}
</script>
<style>
@import '@/assets/base.css';
#app {
width:100%;
height:100%;
display: flex;
flex-direction: column;
align-items: center;
justify-content: center;
}
</style>
