<template>
  <main v-if="character">
    <p>Character Details:</p>
    <p>{{character.name}}</p>
    <p>{{character.species}}</p>
    <p>{{character.status}}</p>
  </main>
</template>

<script>
export default {
    name: "character-details",
    props: ["character"]
}
</script>

<style>

</style>