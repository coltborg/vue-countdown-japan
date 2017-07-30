<template>
  <div id="app">
    <countdown></countdown>
  </div>
</template>

<script>
import Countdown from './components/Countdown';

export default {
  name: 'app',
  components: {
    Countdown,
  },
};
</script>

<style>
body {
  font-family: 'Noto Serif', serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  align-items: center;
  background-image: url('./assets/japan-house.jpg');
  background-size: cover;
  background-position-y: 35%; 
  background-repeat: no-repeat;
  display: flex;
  height: 100vh;
  justify-content: center;
  margin: 0;
  padding: 0;
  text-align: center;
}
</style>
