<template>
  <div class="page-header">
    <button class="page-header__add-task">+ New Task</button>
    <search-block />
  </div>
</template>

<script>
import SearchBlock from './SearchBlock.vue'

export default {
  components: { SearchBlock },
}
</script>

<style lang="scss">
.page-header {
  display: flex;
  justify-content: flex-end;
  align-items: center;
  gap: 41px;
  width: 100%;
  padding: 20px 17px;
  border-bottom: 1px solid $light-lines;

  &__add-task {
    @include reset-button;
    @include hover {
      color: $light-gray;
    }
  }  
}
</style>