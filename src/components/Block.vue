<template>
  <div v-if="showBlock" @click="stopTimer">
    <div class="block w-[400px] rounded-2xl text-3xl font-mono font-bold bg-blue-500  text-white text-center py-24 my-10 mx-auto">
      Click Me
    </div>
  </div>
</template>

<script>
export default {
  name: "Block",
  props: ['delay'],
  data() {
    return {
      showBlock: false,
      timer : null,
      reactionTime: 0,
    }
  },
  mounted() {
    console.log('Component mounted.')
    setTimeout(() => {
        this.showBlock = true
        this.startTimer()
        },this.delay

    )
  },
  updated() {
    console.log('Component updated.')
  },
  unmounted() {
    console.log('Component unmounted.')
  },

methods:{
    startTimer(){
      this.timer= setInterval(()=>{
        this.reactionTime += 10

      },10 )
    },
    stopTimer(){
      clearInterval(this.timer)
      this.$emit('end',this.reactionTime)
      
    },

}

}
</script>

<style >

</style>