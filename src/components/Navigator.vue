<template>
  <div class="navigator">
    <div class="nav">
      <div class="nav-wrapper flex-row">
        <!-- Top Nav -->
        <div class="nav-text left">
          <div class="nav-title">
            <span>anello</span>
          </div>
          <div v-for="item in navItems" :key="item" class="nav-item flex-row">
            <div class="item flex-col">
              {{ item }}
            </div>
          </div>
        </div>
        <div class="nav-content flex-row">
          <div class="nav-timer flex-col">
            <div class="nav-timer-text">
              購物車保留時間 29:15
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
      <div class="nav-bot-wrapper flex-row"></div>
      <!-- Bot Nav End -->
    </div>
  </div>
</template>

<script>
export default {
  name: "Navigator",
  data() {
    return {
      navItems: ["活動", "分類", "EN"],
      svgIcons: ["search", "account", "shopping"]
    };
  }
};
</script>

<style lang="stylus">
.nav
  // Common
  .left
    text-align left
  .flex-col
    display flex
    flex-direction column
  .flex-row
    display flex
    flex-direction row
  .mr-48
    margin-right 48px
  // Common End

  .nav-wrapper
    padding 11px 147px
    align-items center
    justify-content space-between
    .nav-text
      display flex
      flex-direction row
      margin-right 166px
      .nav-title
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
          width 36px
          height 24px
          font-size 18px
          font-family Segoe UI,Bold
          color #333333
          padding-top 11px
          margin-right 50px
          justify-content center
    .nav-content
      align-items flex-end
      .nav-timer
        width 217px
        height 44px
        color #FFFFFF
        background #30303A
        border-radius 5px
        opacity 1
        justify-content center
        margin-right 96px
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
              opacity 1

  .nav-bot-wrapper
    width 1440px
    height 165px
    background #e8e8e8
    opacity 1
    margin-top 50px
</style>
