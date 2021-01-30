<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js + TypeScript App"/>
</template>

<script lang="ts">
import { useQuery } from '@apollo/client';
import gql from 'graphql-tag';
import { defineComponent } from 'vue';
import type { Pokemon } from '@/types/pokemon';
import HelloWorld from './components/HelloWorld.vue';

export default defineComponent({
  name: 'App',
  components: {
    HelloWorld,
  },
  setup() {
    const { data } = useQuery<Pokemon[]>(gql`
      query getPokemons($first: Int!){
        pokemons(first: $first){
          id
          number
          name
          types
          image
        }
      }
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
