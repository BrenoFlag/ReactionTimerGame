<template>
  <div v-if="showBlock" @click="stopTimer">
    <h2>ClickMe</h2>
  </div>
</template>

<script>

  export default {
    props: ['delay'],
    data(){
      return{
        showBlock: false,
        timer: null,
        reactionTime: 0
      }
    },
    methods:{
      startTimer(){
        this.timer = setInterval(()=>{
          this.reactionTime += 10
        })
      },
      stopTimer(){
        clearInterval(this.timer)
        console.log(this.reactionTime)
        this.$emit('close', this.reactionTime)
        this.$data
      }
    },
    mounted() {
      setTimeout(()=>{
        this.showBlock = true
        this.startTimer()
        console.log('Component mounted to the DOM! ' + this.delay)
      }, this.delay)
    },
  }
</script>


<style scoped>
div{
  background: green;
  border-radius: 20px;
  width: 400px;
  color: white;
  text-align: center;
  padding:100px 0;
  margin: 40px auto;
}
</style>