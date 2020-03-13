<template>
  <div class='idea-card'>
    <div class='idea-card-body'>
      <h3>{{idea.title}}</h3>
      <p>{{idea.content}}</p>
    </div>
    <img 
      @click.prevent 
      width=15 
      v-on:click='getId'
      src='https://c7.uihere.com/icons/790/745/177/resource-submission-batch-deletion-203ac133840a54fb2089cd38a031268c.png'/>
  </div>
</template>

<script>
export default {
  name: 'IdeaCard',
  props: {
    idea: Object
  },
  methods: {
    getId: function (id) {
      console.log(this.idea.id)
    }
  }
}
</script>

<style>
  .idea-card {
    border: 2px #FFD465 solid;
    width: 75px;
  }

</style>