<template>
  <div class="pokedex" id="app">
    <div class="pokedex__left">
      <div class="pokedex__top">
        <div class="pokedex__glass"></div>
        <div class="pokedex__red"></div>
        <div class="pokedex__yellow"></div>
        <div class="pokedex__green"></div>
        <div class="pokedex__skew"></div>
      </div>
      <div class="pokedex__mid">
        <chamar-pokemon></chamar-pokemon>
      </div>
    </div>
    <div class="pokedex__right">
      breno
    </div>
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
  #app{
    width: 1200px;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .pokedex{
    &__top{
    height: 100px;
    background-color: #8b0000;
    width: 600px;
    display: flex;
    justify-content: flex-start;
    align-items: center;
    position: relative;
    }
    &__skew{
      width: 300px;
      height: 50px;
      position: absolute;
      background-color: #c00d0d;
      right: 0;
      bottom: 0;
        &::after{
        content: '';
        width: 100px;
        height: 50px;
        background: #c00d0d;
        position: absolute;
        top: 0px;
        left: -40px;
        transform: skewX(335deg);
      }
    }
    &__mid{
      height: 400px;
      margin-top: -16px;
      background-color: #c00d0d;
      display: flex;
      justify-content: center;
    }
    &__img{
      width: 300px;
      height: 200px;
      background: white;
      border-radius: 16px;
      margin-top: 40px;
      img{
        width:100%;
        height: 200px;
        object-fit: contain;
      }
    }
    &__glass{
      width: 60px;
      height: 60px;
      background: radial-gradient(#05fbfb, #29abe3);
      border-radius: 100%;
      border: 3px solid white;
      margin: 0 15px;
      position: relative;
      &::after{
        content: '';
        width: 30px;
        height: 18px;
        margin: 3px 0 0 15px;
        background: #fff;
        opacity: 0.6;
        border-radius: 17px 33px;
        position: absolute;
        top: 5px;
        transform: skew(327deg,10deg);
        animation: glassDance 3s infinite;
      }
    }
    &__red{
      width: 20px;
      height: 20px;
      background: radial-gradient(#fb7b7b, #fb0505);
      border-radius: 100%;
      margin-top: -40px;
      animation: redLight .5s infinite;
      margin-right: 10px;
    }
    &__yellow{
      width: 20px;
      height: 20px;
      background: radial-gradient(#fbfb9b, #fbfb05);
      border-radius: 100%;
      margin-top: -40px;
      animation: yellowLight .5s infinite;
      margin-right: 10px;
    }
    &__green{
      width: 20px;
      height: 20px;
      background: radial-gradient(#b0fb7b, #50fb05);
      border-radius: 100%;
      margin-top: -40px;
      animation: greenLight .5s infinite;
      margin-right: 10px;
    }
  }
@keyframes redLight {
    0%{
      background: radial-gradient(#fb7b7b, #fb0505);
    }
    50%{
      background: radial-gradient(#fb0505, #fb0505);
    }
    100%{
      background: radial-gradient(#fb7b7b, #fb0505);
    }
}
@keyframes yellowLight {
    0%{
      background: radial-gradient(#fbfb9b, #fbfb05);
    }
    50%{
      background: radial-gradient(#fbfb05, #fbfb05);
    }
    100%{
      background: radial-gradient(#fbfb9b, #fbfb05);
    }
}
@keyframes yellowLight {
    0%{
      background: radial-gradient(#b0fb7b, #50fb05);
    }
    50%{
      background: radial-gradient(#50fb05, #50fb05);
    }
    100%{
      background: radial-gradient(#b0fb7b, #50fb05);
    }
}
@keyframes glassDance {
    0%{
      transform: skew(327deg,10deg);
      left: 0;
    }
    50%{
      left: 5px;
      transform: skew(327deg, 25deg);
    }
    100%{
      transform: skew(327deg,10deg);
      left: 0;
    }
}
</style>
