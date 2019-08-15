<template>
  <div id="app">
    <h1>Aula 13/08</h1>
    <h2 :style="{'background-color': selecionada}">Trocar cor do botão Onclick (usando componentes)</h2>
    <Escolha :cores="cores" v-model="selecionada"></Escolha>
  </div>
</template>

<script>
  import Escolha from "@/components/Escolha";
  export default {
    name: "App2",
    components: {Escolha},
    data(){
      return{
        cores: ['blue', 'green', 'red'],
        selecionada: ''
      }
    },
  }
</script>

<style scoped>
  h2{
    color: white;
  }
</style>