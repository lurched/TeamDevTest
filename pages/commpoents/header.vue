<template lang="pug">
  header
    div.nav
      ul
        li.logo
          img(src="@/assets/images/logo.svg", alt="logo")
          a(href="https://market.derender.tech" target="_blank") eRender
        li
          a(href="/whitepaper.pdf" target="_blank")
            div WHITE PAPER
              div.line
        li(@click="$parent.scrollToPosition('service')")
          div VISION
            div.line
        li(@click="$parent.scrollToPosition('tokenomics')")
          div TOKENOMICS
            div.line
        li.market
          a(href="https://market.derender.tech" target="_blank")
            div MARKET
</template>

<script>
</script>

<style lang="scss" scoped>
@font-face {
  font-family: "derender";src: url(@/assets/fonts/derender.woff2) format("woff2"),
  url(@/assets/fonts/derender.woff2) format("woff");
  font-display: swap;
}
header {
  z-index: 10;
  position: sticky;
  top: 0;
  height: 70px;
  background: #000;
  color: #fff;
  .nav {
    margin: 0 auto;
    width: 1200px;
    display: flex;
    ul {
      width: 100%;
      height: 70px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      font-size: 16px;
      li {
        height: 100%;
        padding: 0 10px;
        display: flex;
        align-items: center;
        cursor: pointer;
        a {
          color: #fff;
        }
        &.logo {
          margin-right: 300px;
          font-family: 'derender';
          --wght: 700;
          --wdth: 99.62;
          --slnt: 12;
          --SRIF: 1;
          font-variation-settings: 'wght' var(--wght),'wdth' var(--wdth),'slnt' var(--slnt),'SRIF' var(--SRIF);
          font-size: 24px;
          img {
            width: 50px;
          }
          a {
            margin: 8px 0 0 -8px;
            z-index: 1;
            font-size: 28px;
          }
        }
        &:hover {
          .line {
            width: 100%;
          }
        }
        &.market {
          position: relative;
          background-color: #00E6A0;
          padding: 0 20px;
          a {
            z-index: 2;
            color: #000;
          }
          &:after {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            z-index: -1;
            display: block;
            width: 0;
            height: 100%;
            background-color: #57f8c7;
            transition: all .3s ease;
          }
          &:hover:after {
            width: 100%;
            z-index: 1;
          }
        }
        .line {
          width: 0;
          height: 4px;
          margin-top: 5px;
          margin-bottom: -10px;
          background-color: #00E6A0;
          transition: .3s;
        }
      }
    }
  }
}
</style>
