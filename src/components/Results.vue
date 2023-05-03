<template>
  <p>React time: {{ score }}ms</p>
  <p class="rank">{{rank}}</p>
</template>

<script>
export default {
  props: ['score'],
  data() {
    return {
      rank: null
    }
  },
  mounted() {
    if (this.score < 250) {
      this.rank = 'Ninja Fingers'
    } else if (this.score < 400) {
      this.rank = 'Rapid Reflexes'
    } else {
      this.rank = 'Snail pace...'
    }
  }
}
</script>

<style>
  .rank {
    font-size: 1.4rem;
    color: #0faf87;
    font-weight: bold;
  }

  button {
    background: #0faf87;
    color: white;
    border: none;
    padding: 8px 16px;
    border-radius: 4px;
    font-size: 16px;
    cursor: pointer;
    margin: 10px;
  }

  button[disabled] {
    opacity: 0.5;
    cursor: not-allowed;
  }
</style>