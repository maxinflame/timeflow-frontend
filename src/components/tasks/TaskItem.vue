<template>
  <div class="task">
    <label 
      class="task__checkbox-label"
      :for="title"
    >
      <input class="visually-hidden" :id="title" type="checkbox">
    </label>
    <span>{{ title }}</span>
  </div>
</template>

<script>
export default {
  props: {
    title: String,
  }
}
</script>

<style lang="scss">
.task {
  display: flex;
  align-items: center;
  gap: size(10px);
  position: relative;
  overflow: hidden;
  height: size(68px);
  padding: size(19px) size(17px) size(19px) size(25px);
  border-radius: size(15px);
  background-color: white;

  & + .task {
    margin-top: size(27px)
  }

  &.red {
    &::before {
      background-color: #FC7A7A;
    }
  }

  &.green {
    &::before {
      background-color: #96C8BC;
    }
  }
  
  &::before {
    content: '';
    display: block;
    position: absolute;
    left: 0;
    top: 0;
    height: 100%;
    width: size(10px);
    background-color: $light-gray;
  }

  &__checkbox-label {
    display: block;
    width: size(28px);
    height: size(28px);
    @include empty-checkbox;
    background-size: 100%;
    cursor: pointer;

    &:has(:checked) {
      @include checked-checkbox;
    }
  }
}
</style>