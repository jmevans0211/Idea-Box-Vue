<template>
  <div>
    <IdeaCard v-for='idea in this.ideas' v-bind:idea='idea'/>
  </div>
</template>

<script>
import IdeaCard from './IdeaCard';

export default {
  name: 'Container',
  props: {
    ideas: Array
  },
  components: {
    IdeaCard
  },
  data () {
    return {

    }
  } 
}
</script>

<style>

</style>