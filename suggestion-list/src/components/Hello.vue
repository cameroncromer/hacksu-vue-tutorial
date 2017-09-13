<template>
  <main>
    <input type="text" placeholder="Input new suggestion" v-model="newSuggestion" @keypress.enter="submitSuggestion">
    <ul>
      <li v-for="suggestion in suggestions">{{ suggestion.suggestionText }} <i>{{ suggestion.votes }}</i></li>
    </ul>
  </main>
</template>

<script>
export default {
  name: 'hello',
  data () {
    return {
      newSuggestion: '',
      suggestions: [
        {
          suggestionText: 'Nick needs outta here',
          votes: 1
        }
      ]
    }
  },
  methods: {
    submitSuggestion () {
      var suggestion = {
        suggestionText: this.data.newSuggestion,
        votes: 0
      }
      this.data.suggestions.push(suggestion)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
