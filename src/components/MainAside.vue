<template>
  <header class="main-aside">
    <div class="main-aside__title-wrapper">
      <h1 class="main-aside__title">Timeflow</h1>
      <pin-icon />
    </div>
    <main-menu />
  </header>
</template>

<script>
import PinIcon from './icons/PinIcon.vue';
import MainMenu from './MainMenu.vue';

export default {
  components: { 
    PinIcon,
    MainMenu,
  },
 
}
</script>

<style lang="scss">
.main-aside {
  width: 404px;
  height: 100%;
  background-color: #363945;
  display: block;
  padding: 20px 26px;
  color: #f5f5f5;

  &__title-wrapper {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 40px;
  }

  &__title {
    font-size: 34px;
    line-height: 43px;
    font-weight: 400;
    margin: 0;
  }
}
</style>