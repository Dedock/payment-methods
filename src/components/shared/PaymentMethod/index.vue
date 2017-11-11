<template>
  <a href="#" class="payment-cart">
    <slot name="logo"></slot>
    <p class="payment-cart__name">
      {{ name }}
    </p>
    <div class="payment-cart__icon--wrapper">
      <slot name="tooltip"></slot>
    </div>
  </a>
</template>

<script>
  export default {
    name: 'PaymentMethod',
    data () {
      return {}
    },
    props: {
      name: {
        type: String
      }
    }
  }
</script>

<style lang="scss">
  @import "~colors";

  .payment-cart {
    width: 172px;
    height: 172px;
    position: relative;
    border-radius: 4px;
    background-color: #ffffff;
    box-shadow: 0 1px 1px 0 rgba(215, 216, 219, 0.5);
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    align-items: center;
    text-decoration: none;
    margin-top: 20px;
    transition: all 0.3s;
    margin-right: 20px;

    &:hover {
      box-shadow: 0 5px 10px 0 rgba(45, 52, 64, 0.2);
    }

    &:hover .payment-cart__name {
      color: $blue;
    }

    &:last-child {
      margin-right: auto;
    }

    &__name {
      font-size: 16px;
      line-height: 1.25;
      color: $dark;
      margin-bottom: 25px;
      margin-top: 20px;
    }

    &__icon--wrapper {
      position: absolute;
      top: 10px;
      right: 10px;
    }
  }
</style>
