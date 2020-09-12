<template>
  <div class="container">
    <div>
      <h2>Welcome to the best corny Dad Jokes on the web!</h2>
    </div>
  </div>
</template>

<script>
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
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

</style>
