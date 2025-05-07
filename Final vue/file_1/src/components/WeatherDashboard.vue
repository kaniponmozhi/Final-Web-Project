<template>
  <div class="dashboard-container">
    <h1 class="title">Weather Dashboard</h1>
    <div v-for="item in weatherData" :key="item.id" class="weather-entry">
      <h2>{{ item.location }}</h2>
      <p><strong>Temperature:</strong> {{ item.temperature }}°C</p>
      <p><strong>Condition:</strong> {{ item.weatherCondition }}</p>
      <p><strong>Forecast:</strong> {{ item.forecast }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'WeatherDashboard',
  data() {
    return {
      weatherData: []
    };
  },
  mounted() {
    fetch('http://localhost:3200/weather')
      .then(response => response.json())
      .then(data => {
        this.weatherData = data;
      })
      .catch(error => console.error("Error fetching weather data:", error));
  }
};
</script>

<style scoped>
.dashboard-container {
  padding: 30px;
  max-width: 600px;
  margin: 0 auto;
}

.title {
  text-align: center;
  font-size: 30px;
  margin-bottom: 30px;
  color: #333;
}

.weather-entry {
  background-color: #f0f9ff;
  border: 1px solid #cce7f6;
  border-radius: 10px;
  padding: 20px;
  margin-bottom: 20px;
  box-shadow: 0 2px 6px rgba(0,0,0,0.1);
}

.weather-entry h2 {
  margin-bottom: 10px;
  color: #007acc;
}

.weather-entry p {
  margin: 6px 0;
  font-size: 16px;
}
</style>
