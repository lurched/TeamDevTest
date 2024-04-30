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
    li
      a(
        href="https://birdeye.so/token/HyhvsbDoxNPJYcMUHUopDWeU2ip6FxRatvrYMH6W7UjM?chain=solana"
        target="_blank"
      )
        img(src="~assets/images/birdeye.png", alt="alt")
        |Birdeye
    li
      a(
        href="https://beta.raydium.io/swap/?inputMint=EPjFWdd5AufqSSqeM2qN1xzybapC8G4wEGGkZwyTDt1v&outputMint=HyhvsbDoxNPJYcMUHUopDWeU2ip6FxRatvrYMH6W7UjM"
        target="_blank"
      )
        img(src="~assets/images/raydium.svg", alt="alt")
        |Raydium
</template>

<script>
</script>

<style lang="scss" scoped>
.exchanges {
  width: 1200px;
  margin: 0 auto;
  ul {
    display: flex;
    flex-wrap: wrap;
    li {
      width: 280px;
      height: 140px;
      margin: 0 26px 40px 0;
      padding: 10px;
      font-size: 24px;
      border: 1px solid #ffffff1a;
      border-radius: 8px;
      &:nth-child(4n) {
        margin-right: 0;
      }
      a {
        display: flex;
        justify-content: center;
        flex-direction: column;
        align-items: center;
      }
      img {
        display: block;
        height: 70px;
        margin: 0 auto 10px;
      }
    }
  }
}
</style>
