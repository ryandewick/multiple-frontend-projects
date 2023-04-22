<template>
  <div class="bg-gray-200 h-screen">
    <div class="container mx-auto p-4">
      <h1 class="text-2xl font-bold mb-4">Weather App</h1>
      <div class="flex justify-center items-center mb-4">
        <input
          type="text"
          class="border border-gray-400 p-2 rounded-l-md w-64"
          v-model="searchQuery"
          placeholder="Enter city name"
        />
        <button
          class="bg-blue-500 text-white px-4 py-2 rounded-r-md"
          @click="searchWeather"
        >
          Search
        </button>
      </div>
      <div v-if="weatherData">
        <div class="flex justify-center items-center mb-4">
          <img
            :src="weatherData.current.weather_icons[0]"
            :alt="weatherData.current.weather_descriptions[0]"
          />
          <p class="text-4xl font-bold ml-4">
            {{ weatherData.current.temperature }}&deg;C
          </p>
        </div>
        <div class="text-center">
          <p class="text-2xl font-bold">{{ weatherData.request.query }}</p>
          <p class="text-xl">
            {{ weatherData.current.weather_descriptions[0] }}
          </p>
          <p class="text-lg">
            Feels like {{ weatherData.current.feelslike }}&deg;C
          </p>
        </div>
      </div>
      <div v-else-if="searched">
        <p class="text-lg text-center">
          No weather data found for "{{ searchQuery }}"
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      searchQuery: "",
      weatherData: null,
      searched: false,
    };
  },
  methods: {
    async searchWeather() {
      const apiKey = "5cde5130e0637bee186efa6a08a17b6d";
      const apiUrl = `http://api.weatherstack.com/current?access_key=${apiKey}&query=${this.searchQuery}`;
      try {
        const response = await fetch(apiUrl);
        if (!response.ok) {
          this.searched = true;
          this.weatherData = null;
          return;
        }
        this.searched = false;
        this.weatherData = await response.json();
        console.log(this.weatherData);
      } catch (error) {
        console.error(error);
      }
    },
  },
};
</script>
