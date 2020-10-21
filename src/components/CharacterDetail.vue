<template lang='html'>
<article>
    <h3>{{ character.name }}</h3>
    <p>{{ character.species }}</p>
    <p>{{character.origin.name}}</p>
    <img :src="character.image" alt="character picture">
</article>

  
</template>

<script>

import { eventBus } from '../main.js'

export default {
    name: 'character-detail',
    props: ['character']

}
</script>

<style lang='css' scoped></style>

</style>