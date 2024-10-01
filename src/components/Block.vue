<template>
  <div class="block" v-show="showBlock" @click="stopTimer">
    Dame click!
  </div>
</template>

<script>
export default {
  props: ['delay'],
  data() {
    return {
      showBlock: false,
      timer: null,
      reactionTime: 0
    }
  },
  mounted() {
    setTimeout(() => {
      this.showBlock = true
      this.startTimer()
    }, this.delay)
  },
  methods: {
    startTimer() {
      // start the timer, tick every 10ms
      this.timer = setInterval(() => {
        this.reactionTime += 10
      }, 10)
    },
    stopTimer() {
      // stop the timer
      clearInterval(this.timer)
      this.$emit('end', this.reactionTime)
    }
  }
}
</script>

<style>
  .block {
    width: 200px;
    border-radius: 10px;
    background:  #184979;;
    color: white;
    text-align: center;
    padding: 100px 0;
    margin: 40px auto;
  }
</style>