<template>
  <div id="app">
    <chamar-pokemon></chamar-pokemon>
  </div>
</template>

<script>
import ChamarPokemon from './components/ChamarPokemon.vue'


export default {
  components: { ChamarPokemon },
  name: 'App',

}
</script>

<style lang="scss">
button{
  padding: 10px 20px;
}
</style>
