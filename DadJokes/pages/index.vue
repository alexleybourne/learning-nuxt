<template>
    <div>
      <h2>Welcome to the best corny Dad Jokes on the web!</h2>
      <hr>
      <br>
      <h3>Random Joke:</h3>
      <LineLoader v-if="this.loading" maxWidth="650px" />
      <span><p>{{ this.joke }}</p><CopyClipboard :data="this.joke" /></span>
      <br>
      <button @click='getJoke()' >New joke <ion-icon name="repeat"></ion-icon></button>
    </div>
</template>

<script>
import axios from "axios";

export default {
  transition: 'slide',
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
      loading: true,
    }
  },
  methods: {
    async getJoke() {
      
      const config = {
        headers: {
          'Accept': 'application/json'
        }
      }

      try {
        const res = await axios.get(`https://icanhazdadjoke.com/`, config);
        console.log(res);
        this.joke = res.data.joke;
        this.loading = false;
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

<style lang="scss" scoped>
  p {
    height: 40px;
  }
</style>
