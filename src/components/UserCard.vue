<template>
  <div class="userCard">
    <div class="userDetail">
      <img src="../assets/images/image-jeremy.png" alt="">
      <div>
        <p>Report for</p>
        <h1>Jeremy</h1>
        <h1>Robson</h1>
      </div>
    </div>
    <div class="date">
      <span @click="changeTime('Daily')" :class="[currentTime === 'Daily' ? 'active' : '']">Daily</span>
      <span @click="changeTime('Weekly')" :class="[currentTime === 'Weekly' ? 'active' : '']">Weekly</span>
      <span @click="changeTime('Monthly')" :class="[currentTime === 'Monthly' ? 'active' : '']">Monthly</span>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentTime: "Daily",
    }
  },
  methods: {
    changeTime(value){
      this.currentTime = value;
      this.$emit("changedTime", value)
    },
  }
}
</script>

<style lang="sass">
.userCard
  background-color: hsl(235, 46%, 20%)
  border-radius: 15px
  width: 200px
  height: 400px
  .date
    display: flex
    flex-direction: column
    justify-content: space-evenly
    padding: 5% 9%
    color: white
    height: 100px
    font-size: 13px
    span
      cursor: pointer
      opacity: 0.7
    span.active
      opacity: 1
    span:hover
      opacity: 1
  .userDetail
    border: 15px
    height: 250px
    background-color: #5746ea
    display: flex
    flex-direction: column
    justify-content: center
    padding: 5% 9%
    border-radius: 15px
    img
      border-radius: 50%
      margin-bottom: 20px
      width: 60px
      height: 60px
      border: solid 1px white
    p, h1
      color: white
      font-weight: 300
    p
      margin-bottom: 0
      font-size: 13px
    h1
      margin: 0
      font-size: 30px
    


</style>