<template>
  <nav class="footer bg-gray-100 shadow">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-16">
        <div class="flex-shrink-0">
          <nuxt-link to="/" class="flex items-center">
            <font-awesome-icon
              :icon="['fasr', 'house']"
              class="text-indigo-700 hover:text-indigo-900 text-2xl"
            />
          </nuxt-link>
        </div>
        <div class="flex">
          <nuxt-link
            to="/todolist"
            class="text-gray-600 hover:text-gray-900 px-3 py-2 rounded-md text-sm font-medium"
            ><font-awesome-icon :icon="['fasr', 'list']" class="text-xl"
          /></nuxt-link>
          <nuxt-link
            to="/calculator"
            class="text-gray-600 hover:text-gray-900 px-3 py-2 rounded-md text-sm font-medium"
            ><font-awesome-icon :icon="['fasr', 'calculator']" class="text-xl"
          /></nuxt-link>
          <nuxt-link
            to="/alarm"
            class="text-gray-600 hover:text-gray-900 px-3 py-2 rounded-md text-sm font-medium"
            ><font-awesome-icon :icon="['fasr', 'clock']" class="text-xl" />
          </nuxt-link>
          <nuxt-link
            to="/weather"
            class="text-gray-600 hover:text-gray-900 px-3 py-2 rounded-md text-sm font-medium"
            ><font-awesome-icon :icon="['fasr', 'cloud']" class="text-xl" />
          </nuxt-link>
        </div>
      </div>
    </div>
  </nav>
</template>
