<template>
    <div>
        
        <div class="pokedex__img">
            <img  v-show="pokemonUrl" :src="pokemonUrl" alt="">
        </div>
        
        <div v-for="(type) in pokemonTypes" :key="type.id">
            <p v-for="(name) in type" :key="name.id">{{name.name}}</p>
        </div>
        <input type="text" v-model="temp">
        <button @click="chamaPokemon">Vai</button>
        <p>{{pokemonName}}</p>
    </div>
</template>

<script>
export default {
    data(){
        return{
            pokemon:{},
            temp:'',
            pokemonName:'',
            pokemonUrl:'',
            pokemonTypes:{}
        }
    },
    methods: {
        chamaPokemon(){
            fetch(`https://pokeapi.co/api/v2/pokemon/${this.temp}`)
            .then(r => r.json())
            .then(r => {
                this.pokemon = r
                this.pokemonName = this.pokemon.name 
                this.pokemonUrl = this.pokemon.sprites.front_default
                this.pokemonTypes = this.pokemon.types
                console.log(this.pokemon)
            })
        },
        atribuiNome(){
            this.pokemonName = this.pokemon.nome
        }
    },
}
</script>

<style>

</style>