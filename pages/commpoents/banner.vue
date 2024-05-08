<template lang="pug">
div.banner
  img(src="@/assets/images/banner.webp")
  div.banner-center
    div.title
      | A New Protocol Focusing on Global Resource Sharing in the AGI Field
      p Run On Solana Network
      a(href="/whitepaper.pdf" target="_blank") WhitePaper
</template>

<script>
</script>

<style lang="scss" scoped>
.banner {
  position: relative;
  height: 600px;
  img {
    width: 100%;
    height: 600px;
  }
  &-center {
    position: absolute;
    top: 0;
    z-index: 1;
    width: 100%;
    height: 100%;
    .title {
      width: 1200px;
      height: 100%;
      margin: 0 auto;
      padding: 10px;
      border-radius: 50%;
      font-size: 56px;
      display: flex;
      justify-content: center;
      flex-direction: column;
      align-items: center;
      color: #fff;
      text-align: center;
      p {
        margin-top: 30px;
        font-size: 36px;
        color: #c0c0c0;
      }
      a {
        margin-top: 60px;
        display: flex;
        justify-content: center;
        align-items: center;
        width: 196px;
        height: 54px;
        background: #00E6A0;
        color: #000;
        font-size: 18px;
      }
    }
  }
}
</style>
