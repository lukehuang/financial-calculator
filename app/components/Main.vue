<template>
  <div class="mdl-layout mdl-js-layout mdl-layout--fixed-drawer">
    <div class="mdl-layout__drawer">
      <left-bar></left-bar>
    </div>
    <main class="mdl-layout__content">
      <div class="page-content">
        <router-view keep-alive></router-view>
      </div>
    </main>
  </div>
</template>

<script type="text/babel">
  import LeftBar from './LeftBar.vue'
  import Blank from './Pages/Blank.vue'
  import Breakeven from './Pages/StockBreakeven/StockBreakeven.vue'
  import Income from './Pages/StockIncome/StockIncome.vue'

  export default {
    ready: () => {
      componentHandler.upgradeDom()
    },
    components: {
      LeftBar: LeftBar,
    },
    routes: {
      '/': {
        component: Blank,
      },
      '/breakeven': {
        component: Breakeven,
      },
      '/income': {
        component: Income,
      },
    },
  }
</script>


<style lang="scss" rel="stylesheet/scss">
  @import 'material-design-lite/src/_variables';

  .page-content {
    margin: 2rem;
    background-color: $card-background-color;
  }
</style>
