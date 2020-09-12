<template>
    <div>
      <SearchJokes v-on:search-text="searchText" />
      <Joke v-for="joke in jokes" :key="joke.id" :id="joke.id" :joke="joke.joke"/>
    </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      jokes: [],
      config: {
        headers: {
          'Accept': 'application/json'
        }
      }
    }
  },
  async created() {
    try {
      const res = await axios.get('https://icanhazdadjoke.com/search', this.config);
      this.jokes = res.data.results;
    } catch (err) {
      console.log(err);
    }
  },
  methods: {
    async searchText(text) {
      try {
      const res = await axios.get(`https://icanhazdadjoke.com/search?term=${text}`, this.config);
      this.jokes = res.data.results;
    } catch (err) {
      console.log(err);
    }
    }
  },
  head() {
    return {
      title: "Dad Jokes",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Best place for corny dad jokes",
        }
      ]
    }
  },
}
</script>

<style>
</style>
