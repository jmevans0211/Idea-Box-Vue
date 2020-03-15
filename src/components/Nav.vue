<template>
  <header>
    <h1>Idea Box</h1>
    <form>
      <div>
        <input v-model.lazy='titleInput' placeholder='Enter Idea Title'></input>
        <input v-model.lazy='contentInput' placeholder='Enter Idea'></input>
      </div>
      <button @click.prevent v-on:click='getInputs'>Submit Idea!</button>
      <p v-if='errorMessage'>Please enter both inputs</p>
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
      errorMessage: false,
      favorited: false
    }
  },
  methods: {
    getInputs: function () {
      if (this.titleInput === '' || this.contentInput === '') {
        this.errorMessage = true
      } else {
        let id = Date.now()
        this.$emit('inputs', this.titleInput, this.contentInput, this.favorited, id)
        this.titleInput = '';
        this.contentInput = '';
      }
    }
  }
}
</script>

<style>
  input, button {
    height: 40px;
    font-size: 20px;
    margin: 5px 10px;
    width: 25%;
  }
  button {
    background-color: #36454f;
    color: white;
  }
</style>