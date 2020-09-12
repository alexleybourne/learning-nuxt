<template>
    <div>
      {{ this.joke }}
    </div>
</template>

<script>
import axios from "axios";

export default {
  head() {
    return {
      title: "Dad Joke",
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
      joke: ''
    }
  },
  async created() {
    const config = {
      headers: {
        'Accept': 'application/json'
      }
    }

    try {
      const res = await axios.get(`https://icanhazdadjoke.com/j/${this.$route.params.id}`, config);
      this.joke = res.data.joke
    } catch (err) {
      console.log(err);
    }
  }
}
</script>

<style>
</style>
