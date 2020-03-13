<template>
  <header>
    <h1>Idea Box</h1>
    <form v-on:submit.prevent="getInputs">
      <input v-model.lazy="titleInput" placeholder="Enter Idea Title"></input>
      <input v-model.lazy="contentInput" placeholder="Enter Idea"></input>
      <button v-on:click="getInputs">Submit Idea!</button>
      <p v-if="errorMessage">Please enter something into your search input</p>
    </form>
  </header>
</template>

<script>
export default {
  name: 'Nav',
  data () {
    return {
      titleInput: '',
      contentInput: '',
      errorMessage: false
    }
  },
  methods: {
    getInputs: function () {
      if (this.titleInput || this.contentInput === '') {
        this.errorMessage = true
      } else {
        console.log(this.titleInput, this.contentInput)
      }
    }
  }
}
</script>

<style>

</style>