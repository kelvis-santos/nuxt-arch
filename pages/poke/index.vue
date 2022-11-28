<template>
    <div>
        <div class="container-search">
            <input class="search-input" type="text" ref="inputSearch" name="search" id="search" placeholder="Busque um nome...">
            <button class="btn btn-search" @click="searchPokemon">Pesquisar</button>
            
        </div>
        <!-- name, sprites, status, abilities, moves, height, weight -->
        <pokecard
            v-if="pokeData"
            :name="pokeData.name"
            :sprites="pokeData.sprites"
            :status="pokeData.status"
            :abilities="pokeData.abilities"
            :moves="pokeData.moves"
            :height="pokeData.height"
            :weight="pokeData.weight"
        />
        <error-card
            v-if="isError"
            error-msg="Insira um nome valido!"
        />
    </div>
</template>
<script>
import block from '../../components/block/block.vue';
import errorCard from '../../components/error/error.vue';
import pokecard from '../../components/card/pokecard.vue';
export default {
    components: {
        block,
        errorCard,
        pokecard
    },
    data() {
        return {
            paramSearch: ``,
            isError: false,
            pokeData: null
        }
    },
    methods: {
        async searchPokemon() {
            const poke = this.$refs.inputSearch?.value
            if (poke === "") {
                this.isError = true
                setTimeout(() => {
                    this.isError = false
                }, 2000) 
                return 
            }
            this.pokeData = await this.$axios.$get(`https://pokeapi.co/api/v2/pokemon/${poke}/`)
            console.log(this.pokeData)
        },
        showAlertEmptyInput() {
            if(!this.paramSearch) return false

            return true
        }
    }
}
</script>
<style>
    textarea, input {
        outline: none;
    }
    .container-search {
        width: auto;
        height: 4rem;
        margin: 1rem;
        display: flex;
        align-items: center;
        justify-content: center;
        border: 0.5px;
        border-color: black;
        background-color: blueviolet;
    }
    .search-input {
        width: auto;
        height: 2rem;
        border-radius: 3px;
        -webkit-appearance: none;
    }
    .btn-search {
        background-color:white;
        border-radius: 3px;
        display:inline-block;
        cursor:pointer;
        color: black;
        font-family:Verdana;
        font-size:14px;
        font-weight:bold;
        padding: 6px 11px;
        text-decoration:none;
    }
    .btn-search:active {
        position:relative;
        top:1px;
    }

</style>