<template>
  <div>
    <h3>{{score}}ms | {{score/1000}}s was your reaction time</h3>
    <h3 v-if="showAverage">Your average reaction time is {{(reactionTimeSum/timesPlayed).toFixed(0)}}ms | {{(reactionTimeSum/timesPlayed/1000).toFixed(3)}}s</h3>
  </div>
</template>

<script>
export default {
  props:['score', 'reactionTimeSum', 'timesPlayed'],
  data(){
    return{
      showAverage: false
    }
  },
  methods:{
  },
  mounted() {
    if (this.timesPlayed > 1) {this.showAverage = true}
  }
}
</script>
]

<style scoped>

</style>