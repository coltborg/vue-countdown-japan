<template>
  <div class="container">
    <span>
      <span class="numbers">{{ 100 }}</span> days
    </span>
    <span>
      <span class="numbers">{{ 100 }}</span> hours
    </span>
    <span>
      <span class="numbers">{{ 100 }}</span> mins
    </span>
    <span>
      <span class="numbers">{{ 100 }}</span> secs
    </span>
    <div class="purpose">
      until <span lang="ja">日本</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'countdown',
  data() {
    return {
      countDownDate: new Date('May 1, 2019 00:00:00').getTime(),
      now: Date.now(),
      testing: '',
    };
  },
  mounted() {
    this.now = Date.now();
    this.countdown();
  },
  methods: {
    countdown() {
      setInterval(() => {
        const secondsLeft = Math.round((this.countDownDate - this.now()) / 1000);
        // check if we should stop it!
        // if (secondsLeft < 0) {
        //   clearInterval(countdown);
        //   return;
        // }
        // display it
        this.displayTimeLeft(secondsLeft);
      }, 1000);
    },
    displayTimeLeft(seconds) {
      this.testing = seconds;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container {
  color: #fff;
  background-color: #e0e0e0;
  padding: 2rem;
}
.numbers {
  font-size: 3.5rem;
  font-weight: 300;
}
.purpose {
  font-size: 3rem;
  font-weight: 400;
}
</style>
