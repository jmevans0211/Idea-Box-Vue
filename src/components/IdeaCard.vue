<template>
  <div class='idea-card'>
    <body class='idea-card-body'>
      <h3>{{idea.title}}</h3>
      <p>{{idea.content}}</p>
    </body>
    <footer>
      <img
        class='img-star'
        v-if='idea.favorited === false'
        src='../../images/star.svg'
        width=20
        v-on:click='toggleFavorite'
      />
      <img
        class='img-star' 
        v-if='idea.favorited === true'
        src='../../images/star-active.svg'
        width=20 
        v-on:click='toggleFavorite'
      />
      <img
        class='img-delete'
        @click.prevent 
        width=15 
        v-on:click='getId'
        src='https://c7.uihere.com/icons/790/745/177/resource-submission-batch-deletion-203ac133840a54fb2089cd38a031268c.png'
      />
    </footer>
  </div>
</template>

<script>
export default {
  name: 'IdeaCard',
  props: {
    idea: Object
  },
  methods: {
    getId: function () {
      this.$emit('id', this.idea.id)
    },
    toggleFavorite: function () {
      if (this.idea.favorited === false) {
        this.idea.favorited = true
      } else if (this.idea.favorited === true) {
        this.idea.favorited = false
      }
    }
  }
}
</script>

<style>
  .idea-card {
    border: 5px #36454f solid;
    color: #36454f;
    margin: 10px;
    width: 175px;
  }
  footer {
    background-color: #FFD465;
    border-top: 3px #36454f solid;
  }
  .img-star {
    margin-right: 50px;
    transform: translateY(13%);
  }
  .img-delete {
    margin-left: 50px
  }
</style>