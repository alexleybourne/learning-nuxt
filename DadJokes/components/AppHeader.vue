<template>
  <header class="header">
    <h1 class="title">Dad Jokes.</h1>
      <ul class="menus">
          <li>
              <nuxt-link to="/">Home</nuxt-link>
          </li>
          <li>
              <nuxt-link to="/jokes">Jokes</nuxt-link>
          </li>
          <li>
              <nuxt-link to="/about">About</nuxt-link>
          </li>
          <li>
              <DarkMode />
          </li>
      </ul>
  </header>
</template>

<script>
export default {
  name: 'AppHeader'
}
</script>

<style lang="scss">

@import '~assets/styles.scss';

.header {
    display:flex;
    justify-content:space-between;
    align-items:center;
    margin-top: 2rem;
    margin-bottom: 1rem;
    padding-bottom:1rem;
    border-bottom: 1px dotted $mainColor;
}

.header .title {
    font-size:3rem;
    color: $mainColor;
}

.header ul {
    display:flex;
}

.header a {
    display: inline-block;
    background: $mainColor;
    color: #fff;
    padding: 0.3rem 1rem;
    margin-right: 0.5rem;
    border-radius: 25px;
    transition-duration: 0.4s;

    &:hover {
        transform: scale(1.1);
    }

    &:active {
      transform: scale(0.95);
    }
}

li {
    display: flex;
    align-items: center;
    justify-content: center;
}

@media only screen and (max-width: 600px) {
    ul {
        flex-direction: column;
    }

    li {
        margin: 2px;
        display: flex;
    }
}

</style>
