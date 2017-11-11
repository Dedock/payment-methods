<template>
  <div class="input__wrapper">
    <div :class="['input__content', { 'input__content--active': active }]">
      <search-icon></search-icon>
      <input @focus="toggleActiveClass" @blur="toggleActiveClass" class="input" placeholder="Поиск" type="text"/>
    </div>
  </div>
</template>

<script>
  import searchIcon from 'img/icons/search-icon.svg'

  export default {
    name: 'ExtendableInput',
    data () {
      return {
        active: false
      }
    },
    components: {
      searchIcon
    },
    methods: {
      toggleActiveClass () {
        this.active = !this.active
      }
    }
  }
</script>

<style lang="scss">
  @import "~colors";

  .input {
    border: none;
    background-color: #f8f9fa;
    width: 70px;
    padding-left: 5px;
    outline: none;
    transition: all 0.3s;

    &:focus {
      width: 150px;
    }

    &__content {
      position: absolute;
      height: 36px;
      right: 0;
      top: 0;
      display: flex;
      align-items: center;
      background-color: #f8f9fa;
      padding-bottom: 3px;
      border-bottom: 2px solid $silver;
      transition: all 0.3s;

      &--active {
        border-bottom-color: $blue;

        svg g {
          path:first-of-type {
            fill: $blue
          }
        }
      }
    }

    &__wrapper {
      position: relative;
      transition: all 0.3s;
      width: 90px;

      &--active {
        border-bottom-color: $blue;
      }
    }
  }
</style>
