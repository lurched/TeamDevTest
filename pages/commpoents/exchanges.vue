<template lang="pug">
div.exchanges
  h2.wow.animate__fadeInDown.title EXCHANGES
  ul
    li
      a(
        href="https://jup.ag/swap/USDC-HyhvsbDoxNPJYcMUHUopDWeU2ip6FxRatvrYMH6W7UjM"
        target="_blank"
      )
        img(src="~assets/images/jupiter.svg", alt="alt")
        |Jupiter
</template>

<script>
</script>

<style lang="scss" scoped>
.exchanges {
  width: 1200px;
  margin: 0 auto;
  ul {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    li {
      width: 280px;
      height: 140px;
      margin-bottom: 40px;
      padding: 10px;
      display: flex;
      justify-content: center;
      flex-direction: column;
      align-items: center;
      font-size: 24px;
      border: 1px solid #ffffff1a;
      border-radius: 8px;
      img {
        display: block;
        height: 70px;
        margin: 0 auto 10px;
      }
    }
  }
}
</style>
