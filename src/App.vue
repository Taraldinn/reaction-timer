

<script >
import Result from './components/Result.vue'


import Block from "./components/Block.vue";

export default {
  name: 'App',
  components: {Block, Result},
  data() {
    return {
      isPlaying: false,
      delay: null,
      score : null,
      showResult: false,
    }
  },
  methods: {
    start() {
      // set time amount (ms)
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
    },
    endGame(reactionTime) {
      this.score = reactionTime;
      this.isPlaying = true;
      this.showResult = true;
    },

  },
}
</script>

<template>
  <h1 class="text-slate-900 font-body text-5xl text-center mt-10">WelCome To Reaction Timer</h1>
  <div class="flex justify-center">
  <button @click="start" :disabled="isPlaying" class="mt-10 inline-block px-6 py-2.5 bg-blue-500 text-white font-medium text-xs leading-tight uppercase rounded shadow-md hover:bg-blue-700 hover:shadow-lg focus:bg-blue-700 focus:shadow-lg focus:outline-none focus:ring-0 active:bg-blue-800 active:shadow-lg transition duration-150 ease-in-out">Play</button>
  </div>

  <Block v-if="isPlaying" :delay="delay" @end="endGame"/>
  <Result v-if="showResult" :score="score"/>

</template>

<style scoped>

</style>
