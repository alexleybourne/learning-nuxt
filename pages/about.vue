<template>
  <div class="container">
    <div>
      <h2>The best bad jokes on the internet.</h2>
      <p>Built off this fantastic <a class="blue" href="https://www.youtube.com/watch?v=ltzlhAxJr74">tutorial</a> by <a class="blue" href="https://twitter.com/traversymedia">Brad Traversy</a></p>
      <p>Created with Nuxt.js by Alex Leybourne</p>
    </div>
    <br>
    <div>
      <a href="https://twitter.com/alexleybourne" target="_blank" alt="Twitter" name="Twitter"><ion-icon name="logo-twitter" alt="Twitter"></ion-icon> Follow Me</a>
      <a class="left-space" href="https://github.com/alexleybourne/learning-nuxt" target="_blank" alt="Github" name="Github"><ion-icon name="logo-github" alt="Github"></ion-icon> Github Project</a>
    </div>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: "About the app",
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

<style lang="scss" scoped>

  @import '~assets/styles.scss';

  .blue { color: $mainColor }

  .left-space { margin-left: 14px; }

  ion-icon {
    filter: invert(0);
    font-size: 26px;
    transform: translateY(6px);
  }

  a {
    font-weight: bold;
    transition-duration: 0.4s;

    &:hover {
      color: $mainColor;
      transform: scale(1.1);
    }
  }
</style>
