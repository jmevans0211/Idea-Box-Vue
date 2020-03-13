<template>
  <div>
    <IdeaCard 
      v-for='idea in this.ideas' 
      v-bind:idea='idea' 
      v-bind:id='idea.id'
      @id='deleteCard'
    />
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
  },
  methods: {
    deleteCard: function (id) {
      let idea = this.ideas.find(idea => {
        return idea.id === id
      });

      let index = this.ideas.indexOf(idea);

      this.ideas.splice(index, 1)
      
    }
  }
}
</script>

<style>

</style>