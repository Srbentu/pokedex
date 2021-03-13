<template>
    <div>
        <input type="text" v-model="temp">
        <button @click="chamaPokemon">Vai</button>
        <p>{{pokemonName}}</p>
        <p>{{pokemonTypes}}</p>
        <img v-show="pokemonUrl" :src="pokemonUrl" alt="">
        <div v-for="(type) in pokemonTypes" :key="type.id">
            <p v-for="(name) in type" :key="name.id">{{name.name}}</p>
        </div>
        <div v-for="(name) in pokemonTypes.type" :key="name.id">
            <p>{{name.name}}</p>
        </div>
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