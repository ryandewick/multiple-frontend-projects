<template>
  <div class="alarm">
    <h2>Alarm</h2>
    <div class="max-w-md mx-auto mt-16 px-6 py-4">
      <div class="flex items-center justify-between mb-8">
        <label class="text-xl font-bold">Set Alarm:</label>
        <input
          type="time"
          class="border-2 border-gray-400 rounded-lg px-4 py-2 focus:outline-none focus:border-blue-500"
        />
      </div>
      <div class="flex items-center justify-center">
        <button
          class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded-lg focus:outline-none focus:shadow-outline"
        >
          Set Alarm
        </button>
        <button
          class="bg-red-500 hover:bg-red-700 text-white font-bold py-2 px-4 rounded-lg focus:outline-none focus:shadow-outline ml-4"
        >
          Stop Alarm
        </button>
      </div>
      <div class="flex items-center justify-center mt-8">
        <div v-if="alarmSet" class="flex items-center">
          <svg
            class="animate-spin mr-2 h-5 w-5 text-blue-500"
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
          >
            <circle
              class="opacity-25"
              cx="12"
              cy="12"
              r="10"
              stroke="currentColor"
              stroke-width="4"
            ></circle>
            <path
              class="opacity-75"
              fill="currentColor"
              d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 016 12H2c0 3.042 1.135 5.824 3 7.938l.002-.002zm4-4.829l-.707.707a4 4 0 005.656 0l-.707-.707a3 3 0 01-4.242 0z"
            ></path>
          </svg>
          <span class="text-xl font-bold text-blue-500"
            >Alarm set for {{ alarmTime }}</span
          >
        </div>
        <div v-else>
          <span class="text-xl font-bold text-gray-400">No alarm set</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      alarmSet: false,
    };
  },
};
</script>
