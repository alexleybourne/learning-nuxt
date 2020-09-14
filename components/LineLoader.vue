<template>
  <span></span>
</template>

<script>
export default {
  name: 'LineLoader',
}
</script>

<style lang="scss" scoped>

  @import '~assets/styles.scss';

  span {
    position: absolute;
    transform: translateY(4px);
    transition-duration: 0.1s;
    height: 18px;
    width: 0px;
    border-radius: 2px;
    background: $mainColor;
    animation-name: loading;
    animation-duration: 1s;
    animation-iteration-count: infinite;
  }

  @keyframes loading {
    from {width: 0;}
    to {width: 70vw;}
  }

</style>
