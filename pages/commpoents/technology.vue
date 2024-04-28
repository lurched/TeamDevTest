<template lang="pug">
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
</template>

<script>
export default {
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
  methods: {
    prev() {
      this.$refs.mySwiper.$swiper.slidePrev()
    },
    next() {
      this.$refs.mySwiper.$swiper.slideNext()
    }
  }
}
</script>

<style lang="scss" scoped>
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
</style>
