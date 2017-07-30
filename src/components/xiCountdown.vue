<template>
  <div class="container">
    <div class="block">
      <p class="digit">{{ days | twoDigits }}</p>
      <p class="text">Days</p>
    </div>
    <div class="block">
      <p class="digit">{{ hours | twoDigits }}</p>
      <p class="text">Hours</p>
    </div>
    <div class="block">
      <p class="digit">{{ minutes | twoDigits }}</p>
      <p class="text">Minutes</p>
    </div>
    <div class="block">
      <p class="digit">{{ seconds | twoDigits }}</p>
      <p class="text">Seconds</p>
    </div>
    <div class="purpose">
      <span lang="ja">日本</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'xi-countdown',
  props: {
    date: {
      type: String,
    },
  },
  data() {
    return {
      now: Math.trunc((new Date()).getTime() / 1000),
    };
  },
  computed: {
    normalizedDate() {
      return Math.trunc(Date.parse(this.date) / 1000);
    },
    seconds() {
      return (this.normalizedDate - this.now) % 60;
    },

    minutes() {
      return Math.trunc((this.normalizedDate - this.now) / 60) % 60;
    },

    hours() {
      return Math.trunc((this.normalizedDate - this.now) / 60 / 60) % 24;
    },

    days() {
      return Math.trunc((this.normalizedDate - this.now) / 60 / 60 / 24);
    },
  },
  mounted() {
    window.setInterval(() => {
      this.now = Math.trunc((new Date()).getTime() / 1000);
    }, 1000);
  },
  filters: {
    twoDigits(value) {
      if (value.toString().length <= 1) {
        return `0${value.toString()}`;
      }
      return value.toString();
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import url(https://fonts.googleapis.com/css?family=Oxygen+Mono);
@import url(https://fonts.googleapis.com/earlyaccess/mplus1p.css);

.container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  font-family: 'Oxygen Mono', monospace;
}

.block {
  display: flex;
  flex-direction: column;
  margin: 0 0.5rem;
}

.text,
.purpose {
  color: #ccc;
  font-size: 2.5rem;
  font-size: 2vw;
  font-weight: 700;
  margin: 0;
  text-align: center; 
}

.purpose {
  color: #f5f5f5;
  font-family: "Mplus 1p";
  font-size: 9rem;
  font-size: 10vw;
  font-weight: 500;
  flex-basis: 100%;
}

.digit {
  color: #f5f5f5;
  font-size: 9rem;
  font-size: 9vw;
  font-weight: 400;
  margin: 0 0.5rem;
  text-align: center;
}

@media screen and (max-width: 40em) {
  .text {
    font-size: 4vw;
  }

  .purpose,
  .digit {
    font-size: 15vw;
  }
}

@media screen and (max-width: 30em) {
  .text {
    font-size: 6vw;
  }

  .purpose,
  .digit {
    font-size: 20vw;
  }
}
</style>
