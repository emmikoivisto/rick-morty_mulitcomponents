<template>
  <main>
    <h1>Rick & Morty Character's List</h1>
    <characters-list :characters="characters"></characters-list>
    <character-details :character="selectedCharacter"></character-details>
  </main>
</template>


<script>
import CharactersList from '@/components/CharactersList.vue'
import CharacterDetails from '@/components/CharacterDetails.vue'
import {eventBus} from '@/main.js';

export default {
  name: "app",
  data() {
    return {
      characters: [],
      selectedCharacter: null
    };
  },
  mounted(){
    fetch('https://rickandmortyapi.com/api/character/')
    .then(result => result.json())
    .then(characters => this.characters = characters.results)

    eventBus.$on('character-selected', (character) => {
      this.selectedCharacter = character;
    })
  },
  
  components: {
    "characters-list": CharactersList,
    "character-details": CharacterDetails
  }
}
</script>

<style>

</style>