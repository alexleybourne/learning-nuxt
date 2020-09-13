<template>
  <div>
    <img src="~/assets/loader.gif" />
  </div>
</template>

<script>
export default {
  name: 'Joke',
  props: ['joke', 'id']
}
</script>

<style lang="scss">

  @import '~assets/styles.scss';

  .joke {
    padding: 1rem;
    border: 1px solid #ccc;
    margin: 1rem 0;
    border-radius: 10px;
    transition-duration: 0.4s;

    &:hover {
      color: $mainColor;
      border: 1px solid $mainColor;
    }
  }


</style>
