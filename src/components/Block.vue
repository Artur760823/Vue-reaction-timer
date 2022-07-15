<template>
  <div class="block" v-if="showBlock" @click="stopTimer">
    Click me
  </div>
</template>



<script>
export default {
  props: ['delay'],
  data(){
    return{
      showBlock: false,
      timer: null,
      reactoinTime: 0
    }
  },
  mounted(){
    setTimeout(()=>{
      this.showBlock = true
      this.startTimer()
    }, this.delay)
  },
  methods:{
    startTimer(){
      this.timer = setInterval(()=>{
        this.reactoinTime += 10
      }, 10)
    },
    stopTimer(){ 
      clearInterval(this.timer)
      console.log(this.reactoinTime)
    },

  }

}
</script>

<style>
.block{
  width: 400px;
  border-radius: 20px;
  background-color: #0faf87;
  color: white;
  text-align: center;
  padding: 100px 0;
  margin: 40px auto;
}
</style>