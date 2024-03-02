<template>
  <div class="page-wrapper">
    <main-aside/>
    <div class="page-wrapper__main">
        <page-header />
        <div class="main-wrapper">
          <div class="grid-wrapper">
            <grid-header 
              v-model:isSidebarHidden="isSidebarHidden"
            /> 
          </div>
          <right-sidebar
            :class="{hidden :isSidebarHidden}"
          />
        </div>
    </div>
  </div>
</template>

<script>
import GridHeader from './components/grid/GridHeader.vue'
import MainAside from './components/MainAside.vue'
import PageHeader from './components/PageHeader.vue'
import RightSidebar from './components/right-sidebar/RightSidebar.vue'

export default {
  components: { MainAside, PageHeader, RightSidebar, GridHeader },
  data() {
    return {
      isSidebarHidden: false,
    }
  },
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
    display: flex;
    flex-direction: column;
    height: 100%;
  }
}

.main-wrapper {
  display: flex;
  justify-content: flex-end;
  width: 100%;
  height: 100%;
  flex-basis: 100%;
  flex-shrink: 1;
}

.grid-wrapper {
  width: 100%;
  height: 100%;
}
</style>