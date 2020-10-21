<template>
  <main>
    <h1>Rick & Morty Character's List</h1>
    <characters-list :characters="characters"></characters-list>

  </main>
</template>


<script>
import CharactersList from '@/components/CharactersList.vue'
import CharacterItem from '@/components/CharacterItem.vue'

export default {
  name: "app",
  data() {
    return {
      characters: []
    };
  },
  mounted(){
    fetch('https://rickandmortyapi.com/api/character/')
    .then(result => result.json())
    .then(characters => this.characters = characters.results)
  },
  
  components: {
    "characters-list": CharactersList
  }
}
</script>

<style>

</style>