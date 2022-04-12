<template>
  <div class ='Forca'>
      <img :src="`https://raw.githubusercontent.com/william-costa/wdev-hangman-game-resources/master/images/hangman/${erros}.svg`">
     
  </div>
</template>

<script>
export default {
 name: 'Forca',
 props:{
    erros: Number
 },
 data(){
     return {

     }
 },
 methods:{

 },
 components:{
    
 }
}
</script>

<style>
 .Forca img{
     height: 200px;
 }
</style>