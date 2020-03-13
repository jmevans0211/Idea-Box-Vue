<template>
  <ul>
    <li>{{idea.title}}</li>
    <li>{{idea.content}}</li>
  </ul>
</template>

<script>
export default {
  name: 'IdeaCard',
  props: {
    idea: Object
  }
}
</script>

<style>

</style>