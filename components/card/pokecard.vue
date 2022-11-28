<template>
  <div class="pokecard-container">
    <div class="pokecard-icon">
        <img :src="sprites.front_default" :alt="name.toUpperCase()">
    </div>
    <div class="pokecard-info">
        <p class="pokecard-name">{{ name }}</p>
        <div class="pokecard-skills">
            <p
                v-for="abilitie , index in abilities"
                :key="index"
            >
            {{ abilitie.ability.name }}
            </p>
        </div>
    </div>
  </div>
</template>

<script>
export default {
    name: 'pokecard',
    props: {
        name: {
            type: String,
            default: 'No name found!',
            required: false
        },
        sprites: {
            type: Object | String,
            required: false,
            default: ''
        },
        status: {
            type: Object,
            required: false,
        },
        abilities: {
            type: Array,
            required: false,
        },
        moves: {
            type: Array,
            required: false,
        },
        height: {
            type: Number,
            required: false,
            default: 0
        },
        weight: {
            type: Number,
            required: false,
            default: 0
        }
    }
}
</script>

<style>
    .pokecard-container {
        display: flex;
        background-color: cornflowerblue;
        width: 90%;
        height: 6rem;
        align-items: center;
        justify-content: center;
    }
    .pokecard-icon {
        background-color: cadetblue;
        margin-right: 2rem;
    }
    .pokecard-info {

    }
    .pokecard-name {
        font-weight: bold;
        font-size: 20px;
    }
</style>