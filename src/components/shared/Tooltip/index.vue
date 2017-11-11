<template>
  <div :class="['tooltip__wrapper', `tooltip__wrapper--${position}`, { 'tooltip__wrapper--active': show }]">
    <div :class="['tooltip__content', `tooltip__content--${position}`]">
      <p class="tooltip__title">
        {{ tooltipTitle }}
      </p>
      <p class="tooltip__description">
        {{ tooltipDescription }}
      </p>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'IconWithTooltip',
    data () {
      return {}
    },
    props: {
      position: {
        type: String,
        default: 'bottom'
      },
      tooltipTitle: {
        type: String,
        default: 'test'
      },
      tooltipDescription: {
        type: String,
        default: 'test'
      },
      show: {
        type: Boolean
      }
    }
  }
</script>

<style lang="scss">
  @import "~colors";

  .tooltip {
    &__wrapper {
      position: absolute;
      opacity: 0;
      transition: all 0.3s;
      z-index: 100;
      width: 250px;

      &--active {
        opacity: 1;
      }

      &--bottom {
        left: 50%;
        top: calc(100% + 5px);
        transform: translateX(-50%);
      }

      &--top {
        left: 50%;
        bottom: calc(100% + 5px);
        transform: translateX(-50%);
      }

      &--right {
        top: -10px;
        left: calc(100% + 10px);
      }

      &--left {
        top: -10px;
        right: calc(100% + 10px);
      }
    }

    &__content {
      position: relative;
      padding: 15px;
      border-radius: 4px;
      background-color: $dark;

      &--bottom {
        &:after {
          bottom: 100%;
          left: 50%;
          border: solid transparent;
          content: " ";
          height: 0;
          width: 0;
          position: absolute;
          pointer-events: none;
          border-bottom-color: $dark;
          border-width: 5px;
          margin-left: -5px;
        }
      }

      &--top {
        &:after {
          top: 100%;
          left: 50%;
          border: solid transparent;
          content: " ";
          height: 0;
          width: 0;
          position: absolute;
          pointer-events: none;
          border-top-color: $dark;
          border-width: 5px;
          margin-left: -5px;
        }
      }

      &--right {
        &:after {
          right: 100%;
          top: 22px;
          border: solid transparent;
          content: " ";
          height: 0;
          width: 0;
          position: absolute;
          pointer-events: none;
          border-right-color: $dark;
          border-width: 5px;
          margin-top: -5px;
        }
      }

      &--left {
        &:after {
          left: 100%;
          top: 22px;
          border: solid transparent;
          content: " ";
          height: 0;
          width: 0;
          position: absolute;
          pointer-events: none;
          border-left-color: $dark;
          border-width: 5px;
          margin-top: -5px;
        }
      }

    }

    &__title {
      font-size: 12px;
      font-family: 'SFUIText-Bold';
      line-height: 1.33;
      color: #ffffff;
    }

    &__description {
      font-size: 12px;
      line-height: 1.33;
      color: #ffffff;
      padding-top: 5px;
    }
  }
</style>
