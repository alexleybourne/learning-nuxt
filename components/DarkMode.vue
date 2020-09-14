<template>
  <button @click="darkMode" :title="`Change to ${this.active ? 'Dark Mode' : 'Light Mode'}`" >
    <span :class="this.active || 'dark'">
      <ion-icon name="sunny"></ion-icon>
      <ion-icon name="moon"></ion-icon>
    </span>
  </button>
</template>

<script>
export default {
  name: 'DarkMode',
  data() {
    return {
      active: false
    }
  },
  methods: {
    darkMode() {
      this.active = !this.active
      console.log(this.active)
      document.documentElement.classList.toggle('dark-mode')
    }
  }
}
</script>

<style lang="scss">

  :root {
    transition-duration: 0.2s;
    .container {
      background: #f1f1f1;
    }
  }

  .dark-mode {
    filter: invert(0.9) hue-rotate(180deg);
    background: #fcfcfc;

    .container {
      background: #f1f1f1;
    }
  }

</style>

<style lang="scss" scoped>

  @import '~assets/styles.scss';

  span {
    display: flex;
    flex-direction: column;
    filter: invert(1);
    transform: translateY(29px);
    transition-duration: 0.4s;
  }

  .dark {
    transform: translateY(-29px);
  }

  ion-icon {
    font-size: 26px;
    transform: translateX(-3px);
    margin: 16px 0;
  }

  button {
    overflow: hidden;
    height: 40px;
    width: 40px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    align-self: flex-end;
    margin: 4px;

    &:focus {
      outline: none;
    }
  }
  
</style>
