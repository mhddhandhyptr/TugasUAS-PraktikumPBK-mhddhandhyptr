<template>
    <q-card>
      <q-card-section>
        <div class="text-h6">Weather</div>
      </q-card-section>
      <q-card-section>
        <q-input
          v-model="location"
          label="Enter Location"
          outlined
          @keyup.enter="fetchWeather"
        />
        <q-btn label="Get Weather" @click="fetchWeather" />
      </q-card-section>
      <q-card-section v-if="weatherData">
        <div>{{ weatherData.name }}</div>
        <div>{{ weatherData.weather[0].description }}</div>
        <div>{{ weatherData.main.temp }} °C</div>
      </q-card-section>
      <q-card-section v-if="errorMessage">
        <div class="text-negative">{{ errorMessage }}</div>
      </q-card-section>
    </q-card>
  </template>
  
  <script>
  import axios from 'axios';
  
  export default {
    data() {
      return {
        location: '',
        weatherData: null,
        errorMessage: ''
      };
    },
    methods: {
      async fetchWeather() {
        const apiKey = '3c553b7be91cfa582db0ecb2906cecf3'; // Replace with your actual API key
        const url = `https://api.openweathermap.org/data/2.5/weather?q=${this.location}&units=metric&appid=${apiKey}`;
        try {
          this.errorMessage = ''; // Reset error message
          const response = await axios.get(url);
          this.weatherData = response.data;
        } catch (error) {
          this.weatherData = null; // Reset weather data
          if (error.response) {
            // Server responded with a status other than 2xx
            this.errorMessage = `Error: ${error.response.data.message}`;
          } else if (error.request) {
            // Request was made but no response received
            this.errorMessage = 'Error: No response from server. Please try again.';
          } else {
            // Something else caused the error
            this.errorMessage = `Error: ${error.message}`;
          }
          console.error("Error fetching the weather data: ", error);
        }
      }
    }
  };
  </script>
  
  <style scoped>
  .q-card {
    max-width: 400px;
    margin: 20px auto;
  }
  .text-negative {
    color: #e53935; /* Red color for error messages */
  }
  </style>
  