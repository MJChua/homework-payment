<template>
  <div class="navigator">
    <div class="navigator">
      <div class="nav-wrapper flex-row">
        <!-- Top Nav -->
        <div class="nav-text left">
          <div class="nav-title">
            <span>anello</span>
          </div>
          <div class="nav-item flex-row">
            <div
              v-for="(item, index) in navItems"
              :key="index"
              class="item flex-col"
            >
              {{ item }}
            </div>
          </div>
        </div>
        <div class="nav-content flex-row">
          <div class="nav-timer flex-col">
            <div @click.once="onClick()" class="nav-timer-text">
              <span v-if="type === 'Date'">日期 {{ day }}</span>
              <span v-else>將在 {{ time }} 後結束</span>
            </div>
          </div>
          <div class="icon-wrapper flex-row">
            <div
              v-for="(item, index) in svgIcons"
              :key="index"
              class="nav-icon"
            >
              <div class="icons">
                <img
                  :src="require(`@/assets/icons/${item}.svg`)"
                  class="icons-svg"
                  alt="svg-icon"
                />
              </div>
            </div>
          </div>
        </div>
        <!-- Top Nav End -->
      </div>
      <!-- Bot Nav -->
      <div class="nav-bot">
        <div class="step-wrapper flex-row">
          <div
            v-for="(item, index) in stepItems"
            :key="index"
            class="step-content flex-col"
          >
            <div class="step-content-number flex-col">
              {{ item.step }}
            </div>
            <div class="step-content-title">
              {{ item.title }}
            </div>
          </div>
        </div>
      </div>
      <!-- Bot Nav End -->
    </div>
  </div>
</template>

<script>
import dayjs from "dayjs";

export default {
  name: "Navigator",
  data() {
    return {
      navItems: ["活動", "分類", "EN"],
      svgIcons: ["search", "account", "shopping"],
      stepItems: [
        {
          step: "1",
          title: "選擇款式/數量"
        },
        {
          step: "2",
          title: "購物車/結帳"
        },
        {
          step: "3",
          title: "完成訂購"
        }
      ],
      day: dayjs().format("YYYY-MM-DD"),
      time: "",
      type: "Date"
    };
  },
  methods: {
    onClick() {
      if (this.type === "Date") {
        this.type = "Time";
        this.countDown();
      } else {
        this.type = "Date";
      }
    },
    countDown(seconds = 120) {
      const startCount = () => {
        seconds--;
        this.time = seconds;
        if (seconds <= 0) {
          clearInterval(timer);
          alert("倒數計時結束");
        }
      };
      let timer = setInterval(startCount, 1000);
      startCount();
    },
    beforeDestroy() {
      clearInterval();
    }
  }
};
</script>

<style lang="stylus">
.navigator
  margin-bottom 63px
  // Common Css
  .left
    text-align left
  .flex-col
    display flex
    flex-direction column
    text-align center
  .flex-row
    display flex
    flex-direction row
  .mr-48
    margin-right 48px
  // Common Css End

  .nav-wrapper
    padding 11px 147px 0 147px
    align-items center
    justify-content space-between
    .nav-text
      display flex
      flex-direction row
      .nav-title
        cursor default
        span
          width 163px
          height 81px
          font-size 61px
          font-family Segoe UI,Regular
          margin-right 32px
          color #333333
      .nav-item
        align-items center
        .item
          // width 36px
          // height 24px
          font-size 18px
          font-family Segoe UI,Bold
          font-weight bold
          color #333333
          padding-top 11px
          margin-right 50px
          justify-content center
          cursor default
          &:last-child
            margin 0
          &:hover
            transition all .5s ease
            color #e8e8e8
    .nav-content
      align-items flex-end
      .nav-timer
        width 217px
        height 44px
        font-size 18px
        font-family Segoe UI
        font-weight bold
        color #FFFFFF
        background #30303A
        border-radius 5px
        justify-content center
        margin-right 96px
        transition all .5s ease
        cursor pointer
        &:hover
          color #30303A
          background #fff
        &-text
          text-align center
      .icon-wrapper
        justify-content center
        .nav-icon
          margin-right 48px
          &:last-child
            margin 0
          .icons
            width 50px
            height 50px
            &-svg
              width 50px
              height 50px
            &:hover
              transition all .5s ease
              border-radius 5px
              background: #e8e8e8;

  .nav-bot
    width 100%
    background #e8e8e8
    margin-top 30px
    align-items center
    .step-wrapper
      padding-top 30px
      display flex
      flex-direction row
      justify-content center
      .step-content
        align-items center
        margin-right 100px
        &:last-child
          margin 0
        &-number
          width 60px
          height 60px
          font-size 41px
          font-family Segoe UI,Bold
          color #ffff
          border-radius 5px
          background: #30303a;
          justify-content center
        &-title
          font-size 18px
          font-family Segoe UI,Bold
          font-weight bold
          word-break keep-all
          color #333333
          margin 19px 0 40px 0
</style>
