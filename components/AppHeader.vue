<template>
  <header class="header">
      <div class="logo">
          <img class="header-image" src="~/assets/Emoji.png" />
        <h1 class="title">Dad Jokes</h1>
      </div>
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
      </ul>
  </header>
</template>

<script>
export default {
  name: 'AppHeader'
}
</script>

<style lang="scss">

.header {
    display:flex;
    justify-content:space-between;
    align-items:center;
    margin-bottom: 1rem;
    padding-bottom:1rem;
    border-bottom: 1px dotted #ccc;
}

.logo {
    display:flex;
    align-items:center;
    justify-content:center;
}

.header-image {
    width: 70px;
    height: auto;
}

.header .title {
    font-size:3rem;
    color: #526488;
}

.header ul {
    display:flex;
}

.header a {
    display: inline-block;
    background: #333;
    color: #fff;
    padding: 0.3rem 1rem;
    margin-right: 0.5rem;
    border-radius: 25px;
}

@media only screen and (max-width: 600px) {
    ul {
        flex-direction: column;
    }

    li {
        margin: 2px;
    }
}

</style>
