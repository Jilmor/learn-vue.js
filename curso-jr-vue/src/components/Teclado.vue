<template>
  <div class="teclado">
      <button class="tecla" v-for="(letra,key) in 'abcdefghijklmnopqrstuvwxyz'"
       :key = "key"
       :disabled="verificarLetra(letra)"
       v-on:click="jogar(letra)">
        {{letra}}
      </button>
  </div>
</template>

<script>

export default {

name: "Teclado",
    props: {
       letras: Array,
       verificarLetra: Function,
       jogar: Function
    },
    data(){
        return {

        }
    },
    methods: {

    },
    components: {

    }
}
</script>

<style>
    .teclado{
        display: flex;
        flex-wrap: wrap;
        align-content: center;
        max-width:86%;
        margin-top:20px;
    }
    .tecla{
    margin:5px;
    text-transform: uppercase;
    }
</style>