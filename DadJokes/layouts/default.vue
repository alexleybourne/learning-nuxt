<template>
  <div class="container">
    <AppHeader/>
    <Nuxt />
  </div>
</template>

<script>
  export default {
    head() {
      return {
        title: this.title,
        meta: [
          // hid is used as unique identifier. Do not use `vmid` for it as it will not work
          {
            hid: 'description',
            name: 'description',
            content: 'My custom description'
          }
        ],
        script: [
          {
            src: 'https://unpkg.com/ionicons@5.1.2/dist/ionicons.js'
          }
        ],
      }
    }
  }
</script>

<style lang="scss">

  .background {
    position: absolute;
    height: 100%;
    width: 100%;
    margin: 0;
    padding: 0;
    background: white;
  }

</style>
