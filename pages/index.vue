<template lang="pug">
  section.ai
    header
      div.nav
        ul
          li.logo
            |AIDataShare
            //- img.logo(src="~assets/images/logo.webp", alt="logo")
          li WHITE PAPER
          li SERVICE
          li AIAS
          li STATS
          li ENG
    div.main
      div.banner
        //- img(src="~assets/images/banner.webp", alt="banner")
        div.banner-center
          p AI EQUITY
            br
            .
              SHARING
          p AI WORKS
            br
            .
              TRANSACTIONS
        div.banner-bottom
          p A NEW DECENTRALIZED NETWORK SYSTEM
      div.vision.wow.animate__fadeInUp
        h2.title VISION
        ul
          li
            img(src="~assets/images/vision1.webp", alt="alt")
            p Reduce the cost of AI use, so that AI is more accessible, and globally affordable
            span The operation of AI consumes a lot of computing power and electricity,
              | so it is inevitable to pay for using AI service. However,
              | people in many places around the world cannot get US dollars or electronic payment,
              | and many people cannot afford the cost of AI use due to economic difficulties. AIDataShare Network aims to solve these problems.
          li
            img(src="~assets/images/vision2.webp", alt="alt")
            h3.subtitle Generate revenue for    generative AI creators
            span Because the generation of AI is random,
              |even if you input the same prompt word, the result of each time is different,
              |and the result is totally different from others. Your every attempt becomes a unique,
              |exclusive AI art. Upload your AI work and generative prompts to our network,
              |cast them into NFT and trade them to start your journey for making revenue.
      div.service.wow.animate__fadeInUp
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
      div.AIAS.wow.animate__fadeInUp
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
      div.cryto
        h2.wow.animate__fadeInLeft.title Crypto Markets
        img.wow.animate__zoomIn(src="~assets/images/cryto.webp", alt="alt")
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
      div.stats
        h2.wow.animate__fadeInLeft.title USER STATISTICS
        img.wow.animate__zoomIn(src="~assets/images/user.webp", alt="alt")
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
          .logo {
            font-size: 26px;
            img {
              width: 100px;
              height: 100px;
            }
          }
          width: 100%;
          height: 100px;
          display: flex;
          justify-content: space-between;
          align-items: center;
          font-size: 20px;
        }
      }
    }
    .main {
      .title {
        font-size: 50px;
        text-align: center;
        margin-bottom: 80px;
      }
      .subtitle {
        font-size: 32px;
        margin: 15px 0;
      }
      .banner {
        background: url(~assets/images/banner.webp) no-repeat;
        background-size: 100% auto;
        position: relative;
        height: 900px;

        img {
          z-index: -1;
          position: absolute;
          top: 0;
          left: 0;
          right: 0;
          bottom: 0;
          width: 100%;
          height: 700px;
          object-fit: cover;
        }
        &-center {
          padding: 370px 20px 0;
          display: flex;
          justify-content: space-between;
          font-size: 60px;
          font-weight: bold;
        }
        &-bottom {
          padding: 250px 0 0 160px;
          font-size: 60px;
          font-weight: bold;
        }
      }
      .vision {
        width: 1200px;
        margin: 0 auto;
        padding: 30px 0;
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
              margin: 16px 0;
              font-size: 24px;
            }
            span {
              font-size: 20px;
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
              font-size: 20px ;
              margin-bottom: 20px;
            }
          }
        }
      }
      .AIAS {
        position: relative;
        padding: 100px 0;
        .logo {
          position: absolute;
          width: 200px;
          top: 110px;
          left: 300px;
        }
        p {
          margin: 0 auto;
          width: 400px;
          font-size: 20px;
        }
        ul {
          width: 1200px;
          margin: 40px auto 0;
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
              font-size: 20px;
              text-align: center;
              &:last-child {
                margin: 0;
              }
            }
          }
        }
      }
      .cryto {
        padding: 100px 0;
        width: 1200px;
        margin: 0 auto;
        .title {
          margin-bottom: 20px;
          text-align: left;
        }
        img {
          width: 100%;
          border: 1px solid #ffffff1a;
          border-radius: 8px;
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
              p {
                padding: 0 20px 40px;
                font-size: 24px
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
                  width: 12px;
                  height: 12px;
                  border: 4px solid #759dc0;
                  border-radius: 50%;
                  background-color: #fff;
                  transition: all .2s;
                }
              }
              span {
                display: block;
                padding: 20px 20px;
                font-size: 16px;
                word-wrap:break-word
              }
            }
          }
        }
        .button-prev,.button-next {
          position: absolute;
          top: 180px;
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
      .stats {
        padding: 100px 0;
        width: 1200px;
        margin: 0 auto;
        .title {
          margin-bottom: 20px;
        }
        img {
          width: 100%;
          border: 1px solid #ffffff1a;
          border-radius: 8px;
        }
      }
      .footer {
        width: 1200px;
        height: 386px;
        margin: 0 auto;
        font-size: 30px;
        h2 {
          margin-bottom: 50px;
        }
        ul {
          padding: 20px 0;
          li {
            position: relative;
            padding: 0 20px;
            text-align: left;
            &:before {
              content: "";
                position: absolute;
                top: 15px;
                left: 0;
                box-sizing: border-box;
                width: 12px;
                height: 12px;
                border-radius: 50%;
                background-color: #fff;
                transition: all .2s;
            }
          }
        }
      }
    }
  }
</style>

