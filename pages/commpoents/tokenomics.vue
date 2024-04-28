<template lang="pug">
div.tokenomics.wow.animate__fadeInUp
  h2.wow.animate__fadeInDown.title TOKENOMICS
  div.tokenomics-header
    img.logo(src="~assets/images/logo.svg", alt="alt")
    div.right
      p.subtitle $DeRD, the unity token of DeRender
      span
        | $DeRD is a token issued on the Solana Network, with a total supply of 2,022,113,000, to mark the milestone of OpenAI's official launch of ChatGPT to the public on November 30,2022. Its primary functions are to facilitate payments and staking within the DeRender marketplace. The market value and price of DeRD fluctuate with the trading volume of the market. In the DeRender trading market under the DeRender protocol, $DeRD is the exclusive currency for payments, staking, and other financial activities.
      span The minting address is
        a(href="https://solscan.io/token/HyhvsbDoxNPJYcMUHUopDWeU2ip6FxRatvrYMH6W7UjM" target="_blank") HyhvsbDoxNPJYcMUHUopDWeU2ip6FxRatvrYMH6W7UjM.
      span The rights to issue more tokens or freeze them have been relinquished, allowing for public review and supervision of $DeRD's distribution and usage.
  ul
    li
      span Category
      span Locked period(Months)
      span Vesting Period(Months)
      span Allocation
      span Total Number of Tokens
      span Unlocked at Genesis (TGE)
    li
      span Sharing Reward
      span 1
      span 48
      span 10.00%
      span 202,211,300
      span 0
    li
      span Mining Reward(PoS)
      span 0
      span 48
      span 30.00%
      span 606,633,900
      span 0
    li
      span Advisors
      span 4
      span 12
      span 10.00%
      span 202,211,300
      span 0
    li
      span Core Contributors
      span 12
      span 12
      span 15.00%
      span 303,316,950
      span 0
    li
      span Ecosystem Growth Fund
      span 1
      span 36
      span 15.00%
      span 303,316,950
      span 10%
    li
      span Angel Round
      span 1
      span 9
      span 10.00%
      span 202,211,300
      span 15%
    li
      span Public Sale
      span 0
      span 0
      span 10.00%
      span 202,211,300
      span 100%
    li
      span Total
      span
      span
      span 100.00%
      span 2,022,113,000
      span 13.00%
  span.hint As shown in the table above, to mark the milestone of OpenAI's official launch of ChatGPT to the public on November 30,2022, we set the total supply of $ DeRD at 2,022,113,000. Moreover, the DeRD tokens will not be issued in any form in the future.
</template>

<script>
</script>

<style lang="scss" scoped>
.tokenomics {
  position: relative;
  width: 1200px;
  margin: 0 auto;
  &-header {
    margin-left: 50px;
    display: flex;
    .logo {
      width: 200px;
    }
    .right {
      margin-left: 100px;
      h2 {
        margin-bottom: 10px;
      }
      p {
        width: 800px;
        font-size: 24px;
      }
      span {
        display: block;
        font-size: 18px;
        a {
          margin-left: 5px;
          font-size: 20px;
          color: #fff;
        }
      }
    }
  }
  ul {
    width: 1200px;
    margin: 30px auto 0;
    border: 1px solid #333;
    border-radius: 8px;
    overflow: hidden;
    li {
      display: flex;
      align-items: center;
      border-bottom: 1px solid #333;
      &:last-child {
        border: none;
      }
      span {
        flex: 1;
        display: flex;
        align-items: center;
        justify-content: center;
        width: 198px;
        height: 82px;
        padding: 10px;
        font-size: 24px;
        text-align: center;
        border-right: 1px solid #333;
        &:last-child {
          border: none;
        }
      }
    }
  }
  .hint {
    display: block;
    margin: 10px;
    font-size: 16px;
  }
}
</style>
