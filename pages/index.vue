<template lang="pug">
section.ai
  header
    div.nav
      ul
        li.logo
          img(src="@/assets/images/logo.svg", alt="logo")
          a(href="https://market.derender.tech" target="_blank") eRender
        li
          div WHITE PAPER
            div.line
        li(@click="scrollToPosition('service')")
          div VISION
            div.line
        li(@click="scrollToPosition('aias')")
          div TOKENOMICS
            div.line
        li
          a(href="https://market.derender.tech")
            div MARKET
              div.line
        //- li ENG
  div.main
    div.banner
      img(src="@/assets/images/banner.webp")
      div.banner-center
        div.title
          | A New Decentralized Network Lease Equity Transaction Protocol and the Derivative Trading Market
          p Run On Solana Network
          a(href="https://market.derender.tech" target="_blank") WhitePaper
    div.service.wow.animate__fadeInUp(ref="service")
      h2.wow.animate__fadeInDown.title
        span
         | VISION
        | &
        span
         | SERVICE
      ul
        li.wow.animate__fadeInLeft
          h3.subtitle Accessible, Affordable, and for Everyone AI Sharing Service
          p The operation of AI consumes a lot of computing power and electricity, so it is inevitable to pay for using AI services. However, people in many places around the world cannot get US dollars or use electronic payment. On the other hand, many people cannot afford the cost of AI use due to economic difficulties. DeRender Network aims to solve these problems
        li.wow.animate__fadeInRight
          img(src="~assets/images/service.jpg", alt="alt")
      h3.subtitle AI ACCOUNTS SHARING & OTHERS SHARING
      p Premise: Your AI account password can only be verified by email, mobile phone number or other ways to modify the password, to protect your basic rights and interests
      p On the premise of not affecting your normal use, we suggest you share your AI account for free, but you can also earn revenue from lease it. Our system will give token rewards according to your sharing situation. Sharing account rewards will use a mining mechanism, similar to PoS mining
      p Moreover, DeRender Network can apply in other streaming and music equity sharing, such as Netflix, Disney+, Spotify, and Prime Video ect
    div.recommend(ref="recommend")
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
    div.aias.wow.animate__fadeInUp(ref="aias")
      div.aias-header
        img.logo(src="~assets/images/logo.svg", alt="alt")
        div.right
          p.subtitle $DeRD, the unity token of DeRender
          span
           | $DeRD is a utility token that was launched on the Solana Network in April 2024 to support the development and decentralized ownership of the project.
          br
          | The $DeRD token provides immediate utility as holders become a part of our business model, reaping the rewards with network equity lease and paying for subscriptions with the token.
          br
          | To be a holder is to be an essential part of the project itself. The main utility of the token is for Network Lease Equity Transaction Protocol and the Derivative Trading Market.
          p.subtitle DeRD Tokens Allocation
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
    div.technology.wow.animate__fadeInUp
      h2.title Technology Roadmap
      client-only
        swiper(:options="swiperOption" ref="mySwiper")
          swiper-slide.swiper-slide(
            v-for="(item, index) in technologyData"
            :key="index"
          )
            p {{item.time}}
            div.circle.line
            span(v-for="v in item.desc") {{v}}
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
      h2.wow.animate__fadeInLeft.title Contact us
      p Please contact us for any inquiries related to service and operation.
      ul
        li Email
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
      p Copyright ⓒ 2024 DeRender  All Rights Reserved.

</template>

<script>
import Vue from 'vue'
// import myMixins from '../components/iviewUi'
if (process.browser) { // 在这里根据环境引入wow.js
  var {WOW} = require('wowjs')
}
export default Vue.extend({
  name: 'IndexPage',
  // mixins: [myMixins],
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
        {time: '2023.10', desc: [
          'DeRender core team found the project. ',
          'Proposed the plan to establish the DeRender protocol.'
        ]},
        {time: '2023.12', desc: [
          'Complete the first edition of DeRender protocol rules.',
          'Propose the verification plan.',
          'For better user experience, firstly establish the centralized platform for a period of extensive verification, and then release the decentralized version.'
        ]},
        {time: '2024.4', desc: [
          'Release DeRender Extensive Verification System (DeRender Market preview version).',
          'Issue DeRD tokens.',
          'Initiate the development of a decentralized version.',
          'Develop decentralized version and receive feedback from the extensive validation system proceed simultaneously.'
        ]},
        {time: '2024.12', desc: [
          'Release the official decentralized version of DeRender.'
        ]}
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
  @font-face {
    font-family: "derender";src: url(@/assets/fonts/derender.woff2) format("woff2"),
    url(@/assets/fonts/derender.woff2) format("woff");
    font-display: swap;
  }
  .ai {
    background-color: #000;
    color: #fff;
    header {
      z-index: 10;
      position: sticky;
      top: 0;
      height: 100px;
      background: #000;
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
          font-size: 16px;
          li {
            display: flex;
            align-items: center;
            cursor: pointer;
            a {
              color: #fff;
            }
            &.logo {
              margin-right: 300px;
              font-family: 'derender';
              font-size: 24px;
              --wght: 700;
              --wdth: 99.62;
              --slnt: 12;
              --SRIF: 1;
              font-variation-settings: 'wght' var(--wght),'wdth' var(--wdth),'slnt' var(--slnt),'SRIF' var(--SRIF);
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
        font-size: 48px;
        text-align: center;
        margin: 30px 0;

        span {
          display: inline-block;
          margin: 0 40px;
        }
      }
      .subtitle {
        font-size: 28px;
        line-height: 36px;
        margin: 10px 0;
        color: #00E6A0;
      }
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
      .service {
        width: 1200px;
        margin: 0 auto;
        padding: 50px 0;
        p {
          font-size: 20px ;
          margin-bottom: 10px;
        }
        ul {
          width: 100%;
          display: flex;
          justify-content: space-between;
          li {
            width: 550px;
            img {
              width: 100%;
              border-radius: 8px;
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
              font-size: 18px;
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
                  color: #00E6A0;
                }
                .circle:before {
                  border-color: #00E6A0;
                  transform: scale(1.25)
                }
                span {
                  color: #fff;
                }
              }
              p {
                margin-bottom: 20px;
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
                padding: 0 20px;
                font-size: 20px;
                word-wrap:break-word;
                color: #c0c4cc
              }
            }
          }
        }
        .button-prev,.button-next {
          position: absolute;
          top: 128px;
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
          margin-bottom: 30px;
          color: #fff;
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
      }
    }
  }
</style>

