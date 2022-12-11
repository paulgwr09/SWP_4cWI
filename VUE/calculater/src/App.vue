<template>
  <the-calculator></the-calculator>
  <calcBMI></calcBMI>
</template>

<script>
import TheCalculator from './components/theCalculator.vue';
import calcBMI from './components/calcBMI.vue';

export default {
  name: 'App',
  components: {
    TheCalculator,
    calcBMI
}
}
</script>

<style>
#app {
  font-family: monospace;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 50px;
}

</style>
