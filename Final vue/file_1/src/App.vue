<template>
  <div id="app">
    <WeatherDashboard />
  </div>
</template>

<script>
import WeatherDashboard from './components/WeatherDashboard.vue';

export default {
  name: 'App',
  components: {
    WeatherDashboard
  }
}
</script>

<style>
body {
  margin: 0;
  font-family: timesnewroman;
  background-color: #f3f6f9;
}
</style>
