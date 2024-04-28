<template lang="pug">
section.derender
  main-header
  banner
  service(ref="service")
  potential
  description
  tokenomics(ref="tokenomics")
  exchanges
  technology
  main-footer
</template>

<script>
import MainHeader from './commpoents/header.vue'
import Banner from './commpoents/banner.vue'
import Service from './commpoents/service.vue'
import Potential from './commpoents/potential.vue'
import Description from './commpoents/description.vue'
import Tokenomics from './commpoents/tokenomics.vue'
import Exchanges from './commpoents/exchanges.vue'
import Technology from './commpoents/technology.vue'
import MainFooter from './commpoents/footer.vue'

if (process.browser) {
  var {WOW} = require('wowjs')
}
export default {
  name: 'IndexPage',
  components: {
    MainHeader,
    Banner,
    Service,
    Potential,
    Description,
    Tokenomics,
    Exchanges,
    Technology,
    MainFooter
  },
  mounted() {
    this.$nextTick(() => {
      if (process.browser) {
          new WOW({animateClass: 'animate__animated'}).init()
        }
      })
  },
  methods: {
    scrollToPosition(e) {
      const container = this.$refs[e].$el
      container.scrollIntoView({behavior: 'smooth'})
    }
  }
}
</script>

<style lang="scss">
  .derender {
    background-color: #000;
    color: #fff;
    a {
      color: #fff;
    }
    .title {
      font-size: 48px;
      text-align: center;
      margin: 120px 0 30px;
      color: #00E6A0;

      span {
        display: inline-block;
        margin: 0 40px;
      }
    }
    .subtitle {
      font-size: 28px;
      line-height: 36px;
      margin: 10px 0;
    }
  }
</style>

