<template>
  <span :style="styling"></span>
</template>

<script>
export default {
  name: 'LineLoader',
  props: [
    'height',
    'color',
    'marginTop',
    'delay',
    'maxWidth',
  ],
  data() {
    return {
      styling: {
        height: this.height,
        background: this.color,
        marginTop: this.marginTop,
        animationDelay: this.delay,
        maxWidth: this.maxWidth,
      }
    }
  },
}
</script>

<style lang="scss" scoped>

  @import '~assets/styles.scss';

  span {
    position: absolute;
    transform: translateY(4px);
    transition-duration: 0.1s;
    width: 0px;
    max-width: 700px;
    height: 16px;
    border-radius: 4px;
    background: $mainColor;
    animation-name: loading;
    animation-duration: 1s;
    animation-iteration-count: infinite;
  }

  @keyframes loading {
    from {width: 0;}
    to {width: 50%;}
  }

</style>
