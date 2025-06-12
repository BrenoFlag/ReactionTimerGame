<template>
  <div>
    <h1>How fast is your reaction time?</h1>
    <button @click="start()" :disabled="isPlaying">Start</button>
    <BlockComponent :delay="delay" v-if="isPlaying" @close="gameOver"></BlockComponent>
    <results-component v-if="playedOnce & !isPlaying" :score="score"></results-component>
  </div>

</template>

<script>
import BlockComponent from "@/components/BlockComponent.vue";
import ResultsComponent from "@/components/ResultsComponent.vue";

export default {
  name: 'App',
  components: {
    ResultsComponent,
    BlockComponent
  },
  data(){
    return{
      isPlaying: false,
      playedOnce: false,
      delay: null,
      score: null
    }
  },
  methods:{
    start(){
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true,
      this.playedOnce = true
    },
    gameOver(score){
      this.score = score
      this.isPlaying = false
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
