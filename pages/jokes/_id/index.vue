<template>
    <div>
        <nuxt-link to="/jokes"><ion-icon name="arrow-back-circle-outline"></ion-icon> Back to Jokes</nuxt-link>
        <LineLoader v-if="this.loading" />
        <span><h2>{{ this.joke }}</h2><CopyClipboard :data="this.joke" /></span>
        <hr/>
        <small>Joke ID: {{ $route.params.id }}</small>
    </div>
</template>

<script>
import axios from "axios";

export default {
  transition: 'slide',
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
      joke: '',
      loading: true,
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
      this.loading = false
    } catch (err) {
      console.log(err);
    }
  },
}
</script>

<style lang="scss" scoped>

    @import '~assets/styles.scss';

    h2 {
        margin: 12px 0;
        margin-bottom: 20px;
    }

    small {
        color: lightgrey;
    }

    ion-icon {
        filter: invert(0);
        transform: translateY(2px);
    }

    .button {
        width: 20%;
    }

</style>
