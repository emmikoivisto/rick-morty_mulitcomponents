<template>
  <article>
      <li>Character name: {{character.name}}</li>
  </article>
</template>

<script>
export default {
    name: 'character-detail',
    props: ['character']
}
</script>

<style>

</style>