<template lang="pug">
div.footer
  h2.wow.animate__fadeInLeft.title Contact us
  p Please contact us for any inquiries related to service and operation.
  ul
    li derenderofficial@gmail.com
    li
      a(
        href="https://coinmarketcap.com/community/profile/DeRender/"
        target="_blank"
      ) Coinmarketcap
    li
      a(
        href="https://twitter.com/DeRDofficial"
        target="_blank"
      ) Twitter
    li
      a(
        href="https://medium.com/@derenderofficial"
        target="_blank"
      ) Medium
    li
      a(
        href="https://discord.gg/TDSTFVVH"
        target="_blank"
      ) Discord
  span Copyright ⓒ 2024 DeRender  All Rights Reserved.
</template>

<script>
</script>

<style lang="scss" scoped>
.footer {
  width: 1200px;
  margin: 0 auto;
  padding: 0 0 30px;
  font-size: 16px;
  h2 {
    margin-bottom: 30px;
  }
  color: #c0c4cc;
  ul {
    padding: 20px 0;
    display: flex;
    li {
      position: relative;
      margin-right: 20px;
      a {
        color: #c0c4cc;
        &:hover {
          color: #fff;
        }
      }
      &:hover {
        color: #fff;
      }
      cursor: pointer;
    }
  }
  span {
    font-size: 12px;
  }
}
</style>
