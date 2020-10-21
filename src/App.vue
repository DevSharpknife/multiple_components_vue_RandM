<template lang='html'>
  <main>
    <h1>Rick and Morty</h1>
    <character-list :characters="characters"></character-list>
  </main>
</template>

<script>


import CharacterList from './components/CharacterList.vue'

export default {
  name: 'app',
  data () {
    return {
      characters: [],
      selectedCharacter:null
    };
  },
  mounted(){
    fetch('https://rickandmortyapi.com/api/character/')
    .then(res => res.json())
    .then(characters => this.characters = characters.results);
  },
  
  components: {
    "character-list": CharacterList
  }

}
</script>

<style lang='css' scoped>

</style>
