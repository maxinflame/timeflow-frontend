<template>
  <header class="grid-header">
    <div class="grid-header__date">
      <span>February 2024</span>
      <div class="grid-header__date-buttons">
        <button class="grid-header__date-button grid-header__date-button--prev"></button>
        <button class="grid-header__date-button grid-header__date-button--next"></button>
      </div>

      <button 
        class="sidebar-hide"
        :class="{rotated: isSidebarHidden}"
        @click="$emit('hideSidebar')"
      ></button>
    </div>
  </header>
</template>

<script>
export default {
  props: {
    isSidebarHidden: Boolean,
  },
  emits: {
    hideSidebar: null,
  }
}
</script>

<style lang="scss">
.grid-header {
  padding: size(21px) size(27px) size(21px) size(46px);

  &__date {
    @include subtitle;
    font-weight: 400;
    display: flex;
    gap: size(49px);
    align-items: center;
  }

  &__date-buttons {
    display: flex;
    gap: size(27px);
  }

  &__date-button {
    @include reset-button;
    display: block;
    width: size(25px);
    height: size(25px);
    background-size: 100%;

    &--prev {
      @include chevron-left;
    }

    &--next {
      @include chevron-right;
    }
  }

  .sidebar-hide {
    margin-left: auto;
    @include reset-button;
    @include sidebar-hide;
    background-size: size(24px) size(24px);
    width: size(32px);
    height: size(32px);

    &.rotated {
      transform: rotate(180deg);
    }
  }
}
</style>