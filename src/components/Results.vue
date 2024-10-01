<template>
  <p>Reaction time - {{ score }} ms</p>
  <p class="rank">{{ rank }}</p>
</template>

<script>
export default {
  props: ['score'],
  data() {
    return {
      rank : null
    }
  },
  mounted() {
    if (this.score < 250) {
      this.rank = 'Wow! Que rapidez'
    } else if (this.score < 400) {
      this.rank = 'No esta mal!'
    } else if (this.score < 600) {
      this.rank = 'Mucho que mejorar'
    }else {
      this.rank = 'Lento!'
    }
  }
}
</script>

<style>
  .rank {
    font-size: 1.4em;
    color: #62116e;
    font-weight: bold;
  }
</style>