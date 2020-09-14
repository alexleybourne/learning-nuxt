<template>
  <span class="tooltip">
    <span class="text">{{ text }}</span>
    <slot></slot>
  </span>
</template>

<script>
export default {
  name: 'ToolTip',
  props: ['text'],
  data() {
    return {
      styling: {
        height: this.height,
        background: this.color,
        marginTop: this.marginTop,
        animationDelay: this.delay,
      }
    }
  },
}
</script>

<style lang="scss" scoped>

  @import '~assets/styles.scss';

  .tooltip {
    position: relative;
    display: flex;
    align-self: center;
    width: min-content;
    height: min-content;
  }


  .tooltip .text {
    opacity: 0;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 120px;
    background-color: rgba(0, 0, 0, 0.7);
    color: #fff;
    font-size: 12px;
    text-align: center;
    border-radius: 10px;
    padding: 5px 0;
    
    /* Position the tooltip */
    position: absolute;
    z-index: 2;
    bottom: 20%;
    left: -130%;
    margin-left: -60px;
    transition-duration: 0.3s;
    transform: translateX(6px);
  }

  .tooltip:hover .text {
    opacity: 1;
    transform: translateX(0);
  }
  
</style>
