<template lang="pug">
  section.ai
    header
      div.nav
        ul
          li.logo
            img(src="~assets/images/logo2.png", alt="logo")
            |AIDataShare
          li
            div WHITE PAPER
              div.line
          li(@click="scrollToPosition('service')")
            div SERVICE
              div.line
          li(@click="scrollToPosition('aias')")
            div AIAS
              div.line
          li(@click="scrollToPosition('recommend')")
            div RECOMMEND
              div.line
          //- li ENG
    div.main
      div.banner
        div.banner-center
          | AI EQUITY SHARING  AND AI WORKS TRANSACTIONS
          p A NEW DECENTRALIZED NETWORK SYSTEM
      div.vision.wow.animate__fadeInUp
        h2.title VISION
        div.vision-content
            img(src="~assets/images/vision.png", alt="alt")
            ul
              li
                p.subtitle Generate revenue for    generative AI creators
                span Because the generation of AI is random,
                  |even if you input the same prompt word, the result of each time is different,
                  |and the result is totally different from others. Your every attempt becomes a unique,
                  |exclusive AI art. Upload your AI work and generative prompts to our network,
                  |cast them into NFT and trade them to start your journey for making revenue.
              li
                p.subtitle Reduce the cost of AI use, so that AI is more accessible, and globally affordable
                span The operation of AI consumes a lot of computing power and electricity,
                  | so it is inevitable to pay for using AI service. However,
                  | people in many places around the world cannot get US dollars or electronic payment,
                  | and many people cannot afford the cost of AI use due to economic difficulties. AIDataShare Network aims to solve these problems.
      div.service.wow.animate__fadeInUp(ref="service")
        h2.wow.animate__fadeInDown.title SERVICE
        ul
          li.wow.animate__fadeInLeft
            h3.subtitle AI ACCOUNTS SHARING
            p Premise: Your AI account password can only be verified by email, mobile phone number or other ways to modify the password, to protect your basic rights and interests.
            p On the premise of not affecting your normal use,  we suggest you share your AI account for free, but you can also charge. Our system will give tokens rewards according to your sharing situation. Sharing account rewards can also be regarded as a mining mechanism, similar to POS mining.
          li.wow.animate__fadeInRight
            img(src="~assets/images/service.webp", alt="alt")
            h3.subtitle GENERATIVE AI TRADING
            p It`s time to upload your AI works and generative prompts to our network, mint them into NFTs and trade them to start your journey for making revenue.
      div.recommend(ref="recommend")
        h2.wow.animate__fadeInDown.title RECOMMEND
        ul
          li
            img(src="~assets/images/chatgpt.png", alt="alt")
            |ChatGpt
          li
            img(src="~assets/images/bard.svg", alt="alt")
            |Bard
          li
            img(src="~assets/images/anthropic.svg", alt="alt")
            |Anthropic
          li
            img(src="~assets/images/youchat.webp", alt="alt")
            |YouChat
          li
            img(src="~assets/images/gemini.svg", alt="alt")
            |Gemini
          li
            img(src="~assets/images/midjourney.svg", alt="alt")
            |Midjourney
          li
            img(src="~assets/images/adobe.svg", alt="alt")
            |Adobe Firefly
          li
            img(src="~assets/images/stabie.png", alt="alt")
            |Stable Diffusion
      div.aias.wow.animate__fadeInUp(ref="aias")
        h2.title AIAS（AIDataShareCoin Token）
        img.logo(src="~assets/images/logo.png", alt="alt")
        p AIAS is the only payment method in the transaction services provided by our network.Below is the distribution method of the token:
        ul
          li
            span Sharing Reward (mining)
            span 50%
          li
            span Community operations
            span 10%
          li
            span Investors
            span 10%
          li
            span Founders team
            span 10%
      div.technology
        h2.title Technology Roadmap
        client-only
          swiper(:options="swiperOption" ref="mySwiper")
            swiper-slide.swiper-slide(
              v-for="(item, index) in technologyData"
              :key="index"
            )
              p {{item.time}}
              div.circle.line
              span {{item.desc}}
          div.button-prev(
            @click="prev"
            :class="activeIndex === 0 ? 'disabled' : ''"
          )
            i.swiper-button-prev(slot="button-prev")
          div.button-next(
            @click="next"
            :class="activeIndex === technologyData.length - 4 ? 'disabled' : ''"
          )
            i.swiper-button-next(slot="button-next")
      div.footer
        h2.wow.animate__fadeOutLeft.title Contact us
        p Please contact us for any inquiries related to service and operation.
        ul
          li Email
          li Twitter(X)
          li Facebook
        p Copyright ⓒ 2024 AIDATASHARE  All Rights Reserved.

</template>

<script>
import Vue from 'vue'
if (process.browser) { // 在这里根据环境引入wow.js
  var {WOW} = require('wowjs')
}
export default Vue.extend({
  name: 'IndexPage',
  data() {
    return {
      swiperOption: {
        direction: 'horizontal',
        slidesPerView: 4,
        navigation: {
          nextEl: '.swiper-button-prev',
          prevEl: '.swiper-button-prev'
        },
        on: {
          slideChange:() => {this.activeIndex = this.$refs.mySwiper.$swiper.realIndex}
        }
      },
      activeIndex: 0,
      technologyData: [
        {time: 'March 30th', desc: 'Open the registration online in a centralized way, and give the token rewards to users. Registration is also a way of mining.'},
        {time: 'May 30th', desc: 'Open the AI account sharing and rental service functions in a centralized way, and the corresponding reward mechanism (mining mechanism).'},
        {time: 'August 30th', desc: 'Open the AI work transaction in a centralized way.'},
        {time: 'December 30th', desc: 'The system completes the transformation from centralization to decentralization, and transplantation to Solana.'}
      ]
    }
  },
  mounted() {
    this.$nextTick(() => {
      if (process.browser) {  // 在页面mounted生命周期里面 根据环境实例化WOW
          new WOW({animateClass: 'animate__animated'}).init()
        }
      })
  },
  methods: {
    scrollToPosition(e) {
      const container = this.$refs[e]
      container.scrollIntoView({behavior: 'smooth'})
    },
    prev() {
      this.$refs.mySwiper.$swiper.slidePrev()
    },
    next() {
      this.$refs.mySwiper.$swiper.slideNext()
    }
  }
})
</script>

<style lang="scss" scoped>
  .ai {
    background-color: #021830;
    color: #fff;
    header {
      z-index: 10;
      position: sticky;
      top: 0;
      height: 100px;
      background: linear-gradient(to bottom, #325355, #021830);
      color: #fff;
      .nav {
        margin: 0 auto;
        width: 1200px;
        display: flex;
        ul {
          width: 100%;
          height: 100px;
          display: flex;
          justify-content: space-between;
          align-items: center;
          font-size: 22px;
          li {
            display: flex;
            align-items: center;
            cursor: pointer;
            &.logo {
              margin-right: 300px;
              font-size: 30px;
              img {
                filter: brightness(0) invert(1);
                width: 50px;
                margin-right: 10px;
              }
            }
            &:hover {
              .line {
                width: 100%;
              }
            }
            .line {
              width: 0;
              height: 4px;
              margin-top: 5px;
              margin-bottom: -10px;
              background-color: rgb(0,224,202);
              transition: .3s;
            }
          }
        }
      }
    }
    .main {
      .title {
        font-size: 60px;
        text-align: center;
        margin-bottom: 80px;
      }
      .subtitle {
        font-size: 36px;
        margin: 15px 0;
      }
      .banner {
        background: url(~assets/images/banner.webp) no-repeat;
        background-size: 100% auto;
        position: relative;
        height: 1080px;

        &-center {
          width: 1080px;
          height: 100%;
          margin: 0 auto;
          padding: 10px;
          border-radius: 50%;
          font-size: 60px;
          display: flex;
          justify-content: center;
          flex-direction: column;
          align-items: center;
          text-align: center;
          background-color: rgba(2, 24, 48, 0.55);
          p {
            margin-top: 40px;
            font-size: 40px;
            color: #ffffffb3;
          }
        }
      }
      .vision {
        width: 1200px;
        margin: 0 auto;
        padding: 30px 0;
        &-content {
          width: 100%;
          display: flex;
          align-items: center;
          img {
            width: 400px;
            height: 500px;
            border-radius: 8px;
            object-fit: cover;
            margin-right: 60px;
          }
          ul {
            li {
              p {
                margin: 16px 0;
                font-size: 36px;
              }
              span {
                font-size: 24px;
              }
            }
          }
        }
      }
      .service {
        width: 1200px;
        margin: 0 auto;
        padding: 100px 0;
        ul {
          width: 100%;
          display: flex;
          justify-content: space-between;
          li {
            width: 500px;
            img {
              width: 100%;
              border-radius: 8px;
            }
            p {
              font-size: 24px ;
              margin-bottom: 20px;
            }
          }
        }
      }
      .recommend {
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
      .aias {
        position: relative;
        width: 1200px;
        margin: 0 auto;
        padding: 100px 0;
        .title {
          margin-bottom: 60px;
          text-align: right;
        }
        .logo {
          position: absolute;
          width: 200px;
          top: 110px;
          left: 0;
        }
        p {
          margin: 0 auto;
          width: 650px;
          font-size: 24px;
        }
        ul {
          width: 1200px;
          margin: 60px auto 0;
          border: 1px solid #ffffff1a;
          border-radius: 8px;
          background-color: #ffffff1a;
          li {
            display: flex;
            background-color: #ffffff1a;
            margin: 1px 0 0;
            &:first-child {
              margin: 0;
            }
            span {
              flex: 1;
              margin: 0 1px;
              background-color: #021830;
              padding: 10px;
              font-size: 24px;
              text-align: center;
              &:last-child {
                margin: 0;
              }
            }
          }
        }
      }
      .technology {
        width: 1200px;
        margin: 0 auto;
        position: relative;
        .swiper-container {
          width: 1100px;
          margin: 0 auto;
          .swiper-wrapper {
            position: relative;
            overflow: hidden;
            .swiper-slide {
              width: 275px;
              word-wrap:break-word;
              &:hover {
                p {
                  color: #759dc0;
                }
                .circle:before {
                  border-color: #759dc0;
                  transform: scale(1.25)
                }
              }
              p {
                padding: 0 20px 40px;
                font-size: 30px
              }
              .circle {
                position: absolute;
                top: 60px;
                left: 0;
                width: 100%;
                margin: 0;
                border: none;
                border-top: 2px dashed #ffffff3a;
                &:before {
                  content: "";
                  position: absolute;
                  top: -8px;
                  left: 20px;
                  box-sizing: border-box;
                  width: 14px;
                  height: 14px;
                  border: 4px solid #c0d3d9;
                  border-radius: 50%;
                  background-color: #fff;
                  transition: all .2s;
                }
              }
              span {
                display: block;
                padding: 20px 20px;
                font-size: 24px;
                word-wrap:break-word
              }
            }
          }
        }
        .button-prev,.button-next {
          position: absolute;
          top: 194px;
          width: 50px;
          height: 50px;
          background-color: #ffffff1a;
          border-radius: 50%;
          &.disabled {
            opacity: .35;
            cursor: auto;
            pointer-events: none;
          }
          .swiper-button-prev,.swiper-button-next {
            &:after {
              font-size: 24px;
              font-weight: bold;
              color: #d0d3d9;
            }
            &.swiper-button-disabled {
              opacity: 1;
              cursor: pointer;
            }
          }
        }
        .button-prev {
          left: 0;
        }
        .button-next {
          right: 0;
        }
      }
      .footer {
        width: 1200px;
        margin: 0 auto;
        padding: 140px 0 40px;
        font-size: 24px;
        h2 {
          margin-bottom: 50px;
        }
        ul {
          padding: 40px 0;
          display: flex;
          li {
            position: relative;
            margin-right: 20px;
          }
        }
      }
    }
  }
</style>

