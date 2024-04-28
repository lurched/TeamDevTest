<template lang="pug">
div.potential(ref="potential")
  h2.wow.animate__fadeInDown.title Potential Applications
  ul
    li
      img(src="~assets/images/chatgpt.png", alt="alt")
      |ChatGpt
    li
      img(src="~assets/images/midjourney.svg", alt="alt")
      |Midjourney
    li
      img(src="~assets/images/gemini.svg", alt="alt")
      |Gemini
    li
      img(src="~assets/images/stabie.png", alt="alt")
      |Stable Diffusion
    li
      img(src="~assets/images/adobe.svg", alt="alt")
      |Adobe Firefly
    li
      img(src="~assets/images/netflix.svg", alt="alt")
      |Netflix
    li
      img(src="~assets/images/disney-plus.svg", alt="alt")
      |Disney Plus
    li
      img(src="~assets/images/primevideo.svg", alt="alt")
      |Prime Video
</template>

<script>
</script>

<style lang="scss" scoped>
.potential {
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
