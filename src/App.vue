<template>
  <div id="app">
    <xi-countdown date="May 01, 2019"></xi-countdown>
  </div>
</template>

<script>
import xiCountdown from './components/xiCountdown';

export default {
  name: 'app',
  components: {
    xiCountdown,
  },
};
</script>

<style>
 body {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  align-items: center;
  background-image: url('./assets/japan-house.jpg');
  background-color: darkslategrey;
  background-size: cover;
  background-position-y: 35%; 
  background-repeat: no-repeat;
  height: 100vh;
  justify-content: center;
  margin: 0;
  padding: 0;
} 
#app {
  display: flex;
  background-color: hsla(326, 100%, 62%, 0.4);
  background-image: linear-gradient(225deg, hsla(326, 100%, 62%, 0.5) 0%, hsla(272, 36%, 46%, 0.5) 50%, hsla(205, 64%, 47%, 0.5) 100%); 
  align-items: center;
  justify-content: center;
  width: 100vw;
  height: 100vh;
}
</style>
