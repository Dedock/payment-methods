<template>
  <div class="container">
    <div class="payment__description">
      <div class="payment__sum">
        <p class="payment__sum--title">
          Сумма
        </p>
        <p class="payment__sum--value">
          750 грн
        </p>
      </div>
      <div class="payment__purpose">
        <p class="payment__purpose--title">
          Назначение платежа
        </p>
        <p class="payment__purpose--value">
          Счёт №450012. Оплата покупок в интернет-магазине
          (обувь и одежда Grand Frank)
        </p>
      </div>
      <div class="company-logo">
          <asos></asos>
      </div>
    </div>
    <tabs></tabs>
  </div>
</template>

<script>
  import Tabs from 'shared/Tabs/index.vue'
  import asos from 'img/icons/asos-logo.svg'

  export default {
    name: 'Layout',
    components: {
      Tabs,
      asos
    }
  }
</script>

<style lang="scss">
  @import "~colors";

  .payment {
    &__description {
      display: flex;
      justify-content: space-between;
      padding-top: 50px;
    }

    &__sum {
      &--title {
        font-size: 12px;
        color: $cool-grey;
      }

      &--value {
        font-size: 24px;
        line-height: 1.33;
        color: $dark;
      }
    }

    &__purpose {
      &--title {
        font-size: 12px;
        color: $cool-grey;
      }

      &--value {
        font-size: 16px;
        line-height: 1.25;
        color: $dark;
        max-width: 430px;
        margin-top: 5px;
      }
    }
  }

  .company-logo {
    width: 66px;
    height: 66px;
    display: flex;
    justify-content: center;
    align-items: center;
    align-self: flex-end;
    border-radius: 4px;
    background-color: #ffffff;
    border: solid 1px $silver;
  }
</style>
