<template>
  <p class="text-center text-2xl font-bold font-body mt-10 ">Reaction Timer  {{ score }} MS</p>
  <p class="text-center text-2xl font-bold font-body mt-10 ">{{ rank }}</p>

</template>

<script>
export default {
  name: "Result",
  props: ['score'],
  data(){
    return {
      rank: null,

    }
  },
  mounted(){

    if(this.score < 250){
      this.rank = 'Master'
    
    }
    else if(this.score > 250 && this.score < 500){
      this.rank = 'Good'
    
    }
    else if(this.score > 500 && this.score < 1000){
      this.rank = 'Average'
    
    }
    else{
      this.rank = 'Bad'
    
    }
  }
}
</script>

<style scoped>

</style>