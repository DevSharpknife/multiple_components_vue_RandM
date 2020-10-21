<template lang='html'>
  <section>
      <ul>
          <list-item v-for="(character, id) in characters.results" :key="character.results.id"></list-item>
      </ul>
  </section>
</template>

<script>

import CharacterListItem from './CharacterListItem.vue'; 

export default {
    name: 'character-list',
    props: ['characters'],
    components: {
        "list-item": CharacterListItem
    }
}
</script>

<style lang='css' scoped>

</style>