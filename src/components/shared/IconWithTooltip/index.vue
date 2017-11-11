<template>
  <div :class="['icon__wrapper', `icon__wrapper--${color}`]" @mouseover="showTooltip" @mouseleave="hideTooltip">
    <a class="icon">
      <slot name="icon"></slot>
    </a>
    <Tooltip :position="position" :show="visibleTooltip" :tooltipTitle="tooltipTitle" :tooltipDescription="tooltipDescription"></Tooltip>
  </div>
</template>

<script>
  import Tooltip from 'shared/Tooltip/index.vue'

  export default {
    name: 'IconWithTooltip',
    components: {
      Tooltip
    },
    data () {
      return {
        visibleTooltip: true
      }
    },
    props: {
      position: {
        type: String,
        default: 'bottom'
      },
      color: {
        type: String,
        default: 'transparent'
      },
      tooltipTitle: {
        type: String
      },
      tooltipDescription: {
        type: String
      }
    },
    methods: {
      showTooltip () {
        this.visibleTooltip = true
      },
      hideTooltip () {
        this.visibleTooltip = false
      }
    }
  }
</script>

<style lang="scss">
  @import "~colors";

  .icon {
    display: flex;

    &__wrapper {
      border-radius: 4px;
      padding: 4px;
      cursor: pointer;

      &--transparent {
        border: 1px solid transparent;
      }

      &--blue {
        border: 1px solid $blue;
      }

      &--green {
        border: 1px solid $green-teal;
      }
    }
  }
</style>
