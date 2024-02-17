<template>
  <div class="page-wrapper">
    <main-aside/>
    <div class="page-wrapper__main">
        <page-header />
    </div>
  </div>
</template>

<script>
import MainAside from './components/MainAside.vue'
import PageHeader from './components/PageHeader.vue'

export default {
  components: { MainAside, PageHeader },
}
</script>

<style lang="scss">
.page-wrapper {
  display: flex;
  width: 100%;
  height: 100%;
  align-items: flex-start;

   &__main {
    flex-basis: 100%;
    flex-shrink: 1;
  }
}
</style>