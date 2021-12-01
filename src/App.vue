<template>
  <div id="app">
    <section>
      <div class="section">
        <div>
          <UserCard 
          @changedTime="update"
          />
        </div>
        <div class="cardGrid">
          <Card 
          v-for="(card, index) in cards" 
          :key="index" 
          :title="card.title" 
          :bg_image="card.image" 
          :timeframes="card.timeframes" 
          v-bind:style="{ backgroundColor: card.bg_color }"
          :currentTime="currentTime"
          />
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import UserCard from "./components/UserCard.vue"
import Card from "./components/Card.vue"

// Import des images
import exercise from "./assets/images/icon-exercise.svg";
import play from "./assets/images/icon-play.svg";
import care from "./assets/images/icon-self-care.svg";
import social from "./assets/images/icon-social.svg";
import study from "./assets/images/icon-study.svg";
import work from "./assets/images/icon-work.svg";

export default {
  name: 'App',
  data(){
    return {
      cards: [
        {
          title: "Travail",
          image: work,
          timeframes: {
            daily: {
              current: 5,
              previous: 7
            },
            weekly: {
              current: 32,
              previous: 36
            },
            monthly: {
              current: 103,
              previous: 128
            },
          },
          bg_color: "hsl(15, 100%, 70%)"
        },
        {
          title: "Jeux",
          image: play,
          timeframes: {
            daily: {
              current: 1,
              previous: 2
            },
            weekly: {
              current: 10,
              previous: 8
            },
            monthly: {
              current: 23,
              previous: 29
            },
          },
          bg_color: "hsl(195, 74%, 62%)"
        },
        {
          title: "Études",
          image: study,
          timeframes: {
            daily: {
              current: 0,
              previous: 1
            },
            weekly: {
              current: 4,
              previous: 7
            },
            monthly: {
              current: 13,
              previous: 19
            },
          },
          bg_color: "hsl(348, 100%, 68%)"
        },
        {
          title: "Sport",
          image: exercise,
          timeframes: {
            daily: {
              current: 1,
              previous: 1
            },
            weekly: {
              current: 4,
              previous: 5
            },
            monthly: {
              current: 11,
              previous: 18
            },
          },
          bg_color: "hsl(145, 58%, 55%)"
        },
        {
          title: "Social",
          image: social,
          timeframes: {
            daily: {
              current: 1,
              previous: 3
            },
            weekly: {
              current: 5,
              previous: 10
            },
            monthly: {
              current: 21,
              previous: 23
            },
          },
          bg_color: "hsl(264, 64%, 52%)"
        },
        {
          title: "Soin personnel",
          image: care,
          timeframes: {
            daily: {
              current: 0,
              previous: 1
            },
            weekly: {
              current: 2,
              previous: 2
            },
            monthly: {
              current: 7,
              previous: 11
            },
          },
          bg_color: "hsl(43, 84%, 65%)"
        }

      ],
      currentTime: "Daily"
    }
  },
  components: { UserCard, Card },
  methods: {
    update(value){
      this.currentTime = value;
    }
  }
}
</script>

<style lang="sass">

body
  font-family: 'Rubik', sans-serif
  padding: 0
  margin: 0
  box-sizing: 0
  background-color: hsl(226, 43%, 10%)
  // height: 100vh
  padding: 7% 5%

// #app

.section
  display: flex
  justify-content: center
  align-items: center

.cardGrid
  display: grid
  grid-template-columns: repeat(3, 220px)

</style>
