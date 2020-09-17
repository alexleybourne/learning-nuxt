<template>
    <div>
      <SearchJokes v-on:search-text="searchText" />
      <LineLoader v-if="this.loading" color="#C8C8C8" height="82px" marginTop="12px"/>
      <LineLoader v-if="this.loading" color="#C8C8C8" height="82px" marginTop="122px" delay="0.1s"/>
      <LineLoader v-if="this.loading" color="#C8C8C8" height="82px" marginTop="232px" delay="0.2s"/>
      <Joke v-for="joke in jokes" :key="joke.id" :id="joke.id" :joke="joke.joke"/>
    </div>
</template>

<script>
import axios from "axios";

export default {
  transition: 'slide',
  data() {
    return {
      jokes: [],
      loading: true,
      config: {
        headers: {
          'Accept': 'application/json'
        }
      }
    }
  },
  async created() {
    try {
      this.loading = true
      const res = await axios.get('https://icanhazdadjoke.com/search', this.config);
      this.jokes = res.data.results;
      this.loading = false
    } catch (err) {
      console.log(err);
    }
  },
  methods: {
    async searchText(text) {
      try {
      const res = await axios.get(`https://icanhazdadjoke.com/search?term=${text}`, this.config);
      this.jokes = res.data.results;
      this.loading = false
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

<style lang="scss" scoped>

  div {
    min-height: 400px;
  }
  
</style>
