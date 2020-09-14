<template>
  <button @click="copyToClipboard" ><ion-icon name="copy-outline"></ion-icon></button>
</template>

<script>
export default {
  name: 'CopyClipboard',
  props: ['data'],
  methods: {
    copyToClipboard() {
      console.log(this.data);
      const el = document.createElement('textarea');
      el.value = this.data;
      el.setAttribute('readonly', '');
      el.style.position = 'absolute';
      el.style.left = '-9999px';
      document.body.appendChild(el);
      el.select();
      document.execCommand('copy');
      document.body.removeChild(el);
    }
  }
}
</script>

<style lang="scss" scoped>

  @import '~assets/styles.scss';

  button {
    height: 40px;
    width: 40px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    align-self: flex-end;
    margin: 4px;
  }
  
</style>
