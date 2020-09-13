<template>
    <div>
      <h2>Welcome to the best corny Dad Jokes on the web!</h2>
      <hr>
      <br>
      <h3>Random Joke:</h3>
      <h2>{{ this.joke }}</h2>
      <button @click='getJoke()' >New joke</button>
    </div>
</template>

<script>
import axios from "axios";

export default {
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
  data() {
    return {
      joke: '',
    }
  },
  methods: {
    async getJoke() {

      console.log('POG')
      const config = {
        headers: {
          'Accept': 'application/json'
        }
      }

      try {
        const res = await axios.get(`https://icanhazdadjoke.com/`, config);
        console.log(res);
        this.joke = res.data.joke
      } catch (err) {
        console.log(err);
      }
    }
  },
  created() {
    this.getJoke();
  }
}
</script>

<style>

</style>
