<template>
  <form @submit.prevent="onSubmit">
    <input type="text" v-model="text" placeholder="Search Jokes">
    <button type="submit">Search</button>
  </form>
</template>

<script>
export default {
  name: 'SearchJokes',
  data() {
    return {
      text: ''
    }
  },
  methods: {
    onSubmit() {
      this.$emit('search-text', this.text);
      this.text='';
    }
  }
}
</script>

<style lang="scss">

  @import '~assets/styles.scss';

  form {
    display:flex;
    align-items:center;
    justify-content:center;
  }

  button {
    margin: 0 10px;
  }

</style>
