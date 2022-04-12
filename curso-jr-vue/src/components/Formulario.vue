
<template>
  <div class="Formulario">
     <div class="Formulario-title">
         {{title}}
    </div>
    <input type="text" class="Formulario-input" v-model="inputValue">

    <button :disabled = "inputValue.length === 0" v-on:click="onSubmit">
        {{button}}
        </button>
  </div>
</template>

<script>
export default {
  name: 'Formulario',
  props:{
    title: String,
    button: String,
    action: Function
  },
  data() {
      return {
          inputValue:'',
      }
  },
  methods: {
      onSubmit: function(){
        this.action(this.inputValue);  
        this.inputValue ='';
        this.inputValue ='';
      }
  },
  
}
</script>

<style>
    .Formulario{
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        text-align: center;
        margin-top: 20px;
    }
    .Formulario-input{
        padding: 10px;
        border: 0;
        border-radius: 10px;
        margin: 10px 0px;
        text-align: center;
        color: var(--color-text-dark);
        font-size: 17px;
    }

</style>