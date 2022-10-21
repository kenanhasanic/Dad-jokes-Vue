<template>
  <div>
    <SearchJokes v-on:search-text="searchText"/>
    <Joke v-for="joke in jokes" :key="joke.id" :id="joke.id" :joke="joke.joke"/>
  </div>
</template>

<script>
import axios from 'axios'
import Joke from '../../components/Joke.vue'
import SearchJokes from '../../components/SearchJokes.vue'
export default {

  components: {
  
    SearchJokes,
    Joke
  },
  data(){
    return{
      jokes: []
    }
  },

  async created(){
    const config = {
      headers: {
        Accept: 'application/json'
      }
    };

    const res = await axios.get('https://icanhazdadjoke.com/search', config)
    this.jokes = res.data.results
  },

  methods:{
    async searchText(text){
      console.log("tekst je: "+text)
        const config = {
          headers: {
            Accept: 'application/json'
          }
        };

        const res = await axios.get(`https://icanhazdadjoke.com/search?term=${text}`, config)
        this.jokes = res.data.results
    }
  },

  head(){
          return {
              title: 'Dad Jokes',
              meta:[
                {
                  hid: 'description',
                  name: 'description',
                  content: 'Best place for dad jokes'
                }
              ]
          }
      }
  }
</script>

<style>

</style>