<template>
  <div class="hello">
    <h1>Random Word: </h1>
    <br />
    <p> {{word}}</p>
    <button>Generate Word! </button>
  </div>
</template>

<script>
import Vue from 'vue'
const axios = require('axios')
import AsyncComputed from 'vue-async-computed'
Vue.use(AsyncComputed)

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  AsyncComputed: {
    word: function(){
      // axios api stuff
      const options = {
        headers: {
          "x-rapidapi-host": "wordsapiv1.p.rapidapi.com",
          "x-rapidapi-key": "10295e5e4emsh2a95687b1ab16e0p1d9795jsn7ec0aff1c4aa"
        },
        query: {
          "random": "true"
        }
      }

      axios.get("https://wordsapiv1.p.rapidapi.com/words/", options)
        .then((response) => {
          return response.word
        }).catch((error) => {
          alert('Evan is an idiot')
          return error
        })
      return ''
    }


  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
