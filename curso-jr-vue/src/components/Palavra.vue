<template>
  <div class="Palavra">
      <div class="palavra-letras">
       <div class="palavra-letra" v-for="(letra,key) in palavra" :key="key">
           {{(verificarLetra(letra) || etapa === "enforcado") ? letra : ''}}
       </div>
      </div>
      <div class="dica-palavra">
          {{dica}}
      </div>
  </div>
</template>

<script>
export default {
    name: "Palavra",
    props: {
        palavra: String,
        dica: String,
        verificarLetra: Function,
        etapa: String
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
    .Palavra{
    text-transform: uppercase;
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    }
    .palavra-letras{
        display: flex;
        margin-bottom: 25px;
    }
    .palavra-letra{
        height: 40px;
        width: 40px;
        margin: 0px 8px;
        border: 1px solid var(--color-text-light);
        display: flex;
        justify-content: center;
        align-items: center;
        
    }
</style>