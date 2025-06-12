<template>
  <div>
    <h3>{{score}}ms | {{score/1000}}s was your reaction time, {{praise}}</h3>
    <h3 v-if="showAverage">{{(reactionTimeSum/timesPlayed).toFixed(0)}}ms | {{(reactionTimeSum/timesPlayed/1000).toFixed(3)}}s is your average reaction time</h3>
  </div>
</template>

<script>
export default {
  props:['score', 'reactionTimeSum', 'timesPlayed'],
  data(){
    return{
      showAverage: false,
      praise: null
    }
  },
  methods:{
    setpraise(){
      if (this.score >= 400) this.praise = "Dude, wake up!"
      else if (this.score >= 330) this.praise = "that was pretty slow!"
      else if (this.score >= 370) this.praise = "that was slow!"
      else if (this.score >= 240) this.praise = "that was average!"
      else if (this.score >= 200) this.praise = "that was above average!"
      else if (this.score >= 150) this.praise = "that was fast!"
      else if (this.score >= 110) this.praise = "that was race car driver fast!"
      else this.praise = "that was F1 driver fast!"

    }
  },
  mounted() {
    this.setpraise()
    if (this.timesPlayed > 1) {this.showAverage = true}
  }
}
</script>
]

<style scoped>

</style>