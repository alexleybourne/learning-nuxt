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
        ]
      }
    }
  }
</script>

<style lang="scss">

  $mainColor: #3e97e6;

  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  body {
    font-family:Arial, Helvetica, sans-serif;
    font-size: 1rem;
    line-height: 1.6;
    background: #f4f4f4;
  }

  a {
    color: #666;
    text-decoration: none;
  }

  ul {
    list-style: none;
  }

  .container {
    max-width: 800px;
    margin: 2rem auto;
    overflow: hidden;
    padding: 1rem 2rem;
    background: #fff;
  }

  input {
    width: 50%;
    padding: 12px 20px;
    margin: 8px 0;
    display: inline-block;
    border: 1px solid #ccc;
    border-radius: 4px;
    box-sizing: border-box;
  }

  button {
    background-color: $mainColor;
    border: none;
    color: white;
    padding: 10px;
    border-radius: 5px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    cursor: pointer;
    transition-duration: 0.4s;

    &:hover {
        transform: scale(1.1);
    }
  }

</style>
