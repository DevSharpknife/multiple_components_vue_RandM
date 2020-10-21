<template lang='html'>
  <main>
    <h1>Rick and Morty</h1>
    <label for="selected_character">Select a character</label>
    <select id="selected_character" v-model="selectedCharacter">
    <option v-for="(character, id) in characters" :key="character.name" :character="character" :value="character">{{ character.name }}</option>
    </select>

    
    <!-- <character-list :characters="characters"></character-list> -->
    <character-detail :character="selectedCharacter"></character-detail>
  </main>
</template>

<script>


import CharacterList from './components/CharacterList.vue'
import CharacterDetail from './components/CharacterDetail.vue'
import { eventBus } from '@/main.js';

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
    
    eventBus.$on('character-selected', (character) => {
      this.selectedCharacter = character
    })
  },
  
  components: {
    "character-list": CharacterList,
    "character-detail": CharacterDetail
  }

}
</script>

<style lang='css' scoped>

</style>
