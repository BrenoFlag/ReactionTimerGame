<template>
  <div>
    <h3>{{score}}ms | {{score/1000}}s was your reaction time</h3>
  </div>
</template>

<script>
export default {
  props:['score'],
  data(){
    return{

    }
  },
  methods:{

  }
}
</script>
]

<style scoped>

</style>