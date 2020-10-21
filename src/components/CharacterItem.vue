<template>
  <article>
      <li v-on:click="handleClick">Character name: {{character.name}}</li>
  </article>
</template>

<script>
import {eventBus} from '@/main.js';

export default {
    name: 'character-item',
    props: ['character'],

    methods: {
      handleClick() {
      eventBus.$emit('character-selected', this.character);
    }
  }
}
</script>

<style>

</style>