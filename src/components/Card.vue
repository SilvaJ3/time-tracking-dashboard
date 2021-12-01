<template>
  <div class="card" :style="style">
    <div class="activity">
      <div class="title">
        <h1>{{ title }}</h1>
        <img src="../assets/images/icon-ellipsis.svg" alt="">
      </div>
      <div class="time">
        <h1>{{ currentTime === "Daily" ? timeframes.daily.current : currentTime === "Weekly" ? timeframes.weekly.current  : timeframes.monthly.current }}hrs</h1>
        <span>{{ currentTime === "Daily" ? "Yesterday" : currentTime === "Weekly" ? "Last Week" : "Last Month" }} - {{ currentTime === "Daily" ? timeframes.daily.previous : currentTime === "Weekly" ? timeframes.weekly.previous  : timeframes.monthly.previous }} hrs</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props:{
    currentTime: String,
    title: String,
    bg_image: String,
    timeframes: Object,
  },
  computed: {
    style(){
      return "background-image: url('" + this.bg_image + "')"
    },
  }
}

</script>

<style lang="sass">
.card
  border-radius: 15px
  height: 190px
  width: 200px
  color: white
  margin: 5% 10%
  display: flex
  flex-direction: column
  justify-content: end
  background-repeat: no-repeat
  background-position-x: 90%
  background-position-y: -7%
  background-size: 30%
  .activity
    height: 140px
    border-radius: 15px
    padding: 5% 9%
    display: flex
    flex-direction: column
    justify-content: space-around
    background-color: rgba(28, 31, 74, 1)
    z-index: 2
    h1
      margin: 0
      font-weight: 300
    .title
      display: flex
      align-items: center
      justify-content: space-between
      h1
        font-size: 15px
      img
        height: 5px
    .time
      h1
        font-size: 35px
      span
        font-size: 12px
      span:hover
        cursor: pointer
  .activity:hover
    filter: brightness(1.75)

</style>