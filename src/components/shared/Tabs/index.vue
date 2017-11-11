<template>
  <div class="tabs__wrapper">
    <div class="tabs__navigation">
      <div :class="['tabs__navigation--item',{'tabs__navigation--item-active': activeTab === 'all'}]"
           @click="selectTab('all')">Все способы оплаты
      </div>
      <div :class="['tabs__navigation--item',{'tabs__navigation--item-active': activeTab === 'cash'}]"
           @click="selectTab('cash')">Наличные
      </div>
      <div :class="['tabs__navigation--item',{'tabs__navigation--item-active': activeTab === 'credit'}]"
           @click="selectTab('credit')">Безналичные
      </div>
      <div :class="['tabs__navigation--item',{'tabs__navigation--item-active': activeTab === 'electronic'}]"
           @click="selectTab('electronic')">Электронные
      </div>
      <div class="tabs__icon">
        <icon-with-tooltip>
          <location slot="icon"></location>
        </icon-with-tooltip>
      </div>
      <custom-input class="tabs__search"></custom-input>
    </div>
    <transition-group name="fade" mode="out-in">
      <div class="tab" key="all" v-show="activeTab === 'all'">
        <payment-method name="Оплата Картами">
          <bitcoin slot="logo"></bitcoin>
        </payment-method>
        <payment-method name="Оплата Картами">
          <qiwi slot="logo"></qiwi>
        </payment-method>
        <payment-method name="Оплата Картами">
          <bitcoin slot="logo"></bitcoin>
        </payment-method>
        <payment-method name="Оплата Картами">
          <bitcoin slot="logo"></bitcoin>
        </payment-method>
        <payment-method name="Оплата Картами">
          <webmoney slot="logo"></webmoney>
        </payment-method>
        <payment-method name="Оплата Картами">
          <bitcoin slot="logo"></bitcoin>
        </payment-method>
        <payment-method name="Оплата Картами">
          <yandex slot="logo"></yandex>
          <icon-with-tooltip slot="tooltip" color="green">
            <location slot="icon"></location>
          </icon-with-tooltip>
        </payment-method>
        <payment-method name="Оплата Картами">
          <bitcoin slot="logo"></bitcoin>
          <icon-with-tooltip slot="tooltip" position="right" color="blue">
            <external slot="icon"></external>
          </icon-with-tooltip>
        </payment-method>
      </div>
      <div class="tab" key="cash" v-show="activeTab === 'cash'">
        <payment-method name="Оплата Картами">
          <bitcoin slot="logo"></bitcoin>
          <icon-with-tooltip slot="tooltip" position="right" color="blue" tooltipTitle="Some title" tooltipDescription="Some more description fsdfsdfsd fsdfsdfs  dfsdfsd fsdfsdfsdfsdf sdfsdfsdf">
            <external slot="icon"></external>
          </icon-with-tooltip>
        </payment-method>
        <payment-method name="Оплата Картами">
          <bitcoin slot="logo"></bitcoin>
        </payment-method>
        <payment-method name="Оплата Картами">
          <yandex slot="logo"></yandex>
          <icon-with-tooltip slot="tooltip" color="green" tooltipTitle="Some title" tooltipDescription="Some more description fsdfsdfsd fsdfsdfs  dfsdfsd fsdfsdfsdfsdf sdfsdfsdf">
            <location slot="icon"></location>
          </icon-with-tooltip>
        </payment-method>
      </div>
    </transition-group>
  </div>
</template>

<script>
  import PaymentMethod from 'shared/PaymentMethod/index.vue'
  import IconWithTooltip from 'shared/IconWithTooltip/index.vue'
  import CustomInput from 'shared/SearchInput/index.vue'
  import bitcoin from 'img/icons/Bitcoin-logo.svg'
  import qiwi from 'img/icons/Visa-Qiwi_Wallet-icon.svg'
  import webmoney from 'img/icons/Webmoney-logo.svg'
  import yandex from 'img/icons/Yandex-Money-logo.svg'
  import location from 'img/icons/location-icon.svg'
  import external from 'img/icons/badge-external-systems-icon.svg'

  export default {
    name: 'Tabs',
    data () {
      return {
        activeTab: 'all'
      }
    },
    components: {
      PaymentMethod,
      IconWithTooltip,
      CustomInput,
      bitcoin,
      webmoney,
      yandex,
      qiwi,
      location,
      external
    },
    methods: {
      selectTab (chosenTab) {
        this.activeTab = chosenTab
      }
    }

  }
</script>

<style lang="scss">
  @import "~colors";

  .tabs {
    &__wrapper {
      margin-top: 60px;
    }

    &__navigation {
      display: flex;
      justify-content: flex-start;
      padding-bottom: 4px;
      border-bottom: 2px solid $silver;

      &--item {
        font-size: 12px;
        line-height: 1.33;
        color: $dark;
        margin-right: 40px;
        padding-bottom: 10px;
        margin-bottom: -6px;
        border-bottom: 2px solid transparent;
        transition: all 0.3s;
        cursor: pointer;

        &-active {
          font-family: 'SFUIText-Bold';
          line-height: 1.33;
          color: $blue;
          border-color: $blue;
        }
      }
    }

    &__icon {
      position: relative;
      margin-left: auto;
      margin-right: 20px;
    }
  }

  .tab {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
  }
</style>
