<template>
  <!-- <div v-for="pokemon in data.pokemons" :key="pokemon.id">
    <h2>{{ pokemon.name }}</h2>
  </div> -->
  <div>Hello world</div>
</template>

<script lang="ts">
import { useQuery } from '@apollo/client';
import gql from 'graphql-tag';
import { defineComponent } from 'vue';
import type { Pokemon } from '@/types/pokemon';

export default defineComponent({
  name: 'App',

  setup() {
    const { data, loading, error } = useQuery<Pokemon[]>(gql`

    `);
  },
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
