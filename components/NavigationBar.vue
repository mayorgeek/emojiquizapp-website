<template>
  <div>

    <!-- Desktop Navbar -->
    <div class="hidden shadow-md lg:flex lg:justify-between items-center px-16 py-4">
      <!-- Site Logo Image -->
      <div>
        <NuxtLink to="/" class="flex items-center space-x-4">
          <img class="w-10 rounded-md" src="/emojiquizapp-icon.png" alt="Emoji Quiz App Logo">
          <h2 class="text-primary font-medium text-xl">Emoji Quiz App</h2>
        </NuxtLink>
      </div>

      <!-- Navigation Links -->
      <div>
        <ul class="flex items-center space-x-6">
          <li class="text-primary text-lg">
            <NuxtLink to="/">Reviews</NuxtLink>
          </li>
          <li class="text-primary text-lg">
            <NuxtLink to="/">Report</NuxtLink>
          </li>
        </ul>
      </div>
    </div>
    <!-- End of Desktop Navbar -->


    <!-- Mobile Navbar -->
    <div class="lg:hidden">
      <div class="shadow-md flex justify-between items-center px-8 py-2">
        <!-- Site Logo -->
        <div>
          <NuxtLink to="/" class="flex items-center space-x-4">
            <img class="w-8 rounded-md" src="/emojiquizapp-icon.png" alt="Emoji Quiz App Logo">
            <h2 class="text-primary font-medium text-lg">Emoji Quiz App</h2>
          </NuxtLink>
        </div>

        <!-- Mobile Menu Open Button -->
        <button type="button" aria-label="Open Menu" title="Open Menu"
          class="mt-3 p-2 -mr-1 transition duration-200 rounded focus:outline-none focus:shadow-outline"
          @click="drawer">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-primary" fill="none" viewBox="0 0 24 24"
            stroke="currentColor" stroke-width="2">
            <path stroke-linecap="round" stroke-linejoin="round" d="M4 6h16M4 12h16m-7 6h7" />
          </svg>
        </button>
      </div>


      <transition enter-class="opacity-0" enter-active-class="ease-out transition-medium" enter-to-class="opacity-100"
        leave-class="opacity-100" leave-active-class="ease-out transition-medium" leave-to-class="opacity-0">
        <div v-show="isOpen" class="z-10 fixed inset-0 transition-opacity">
          <div @click="isOpen = false" class="absolute inset-0 bg-gray-900 opacity-50" tabindex="0"></div>
        </div>
      </transition>
      <aside
        class="transform top-0 left-0 w-64 bg-white fixed h-full overflow-auto ease-in-out transition-all duration-300 z-30"
        :class="isOpen ? 'translate-x-0' : '-translate-x-full'">


        <!-- Mobile Menu Close Button -->
        <div class="flex flex-row-reverse pt-5 px-6 mb-2">
          <button type="button" @click="isOpen = false">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-primary" fill="none" viewBox="0 0 24 24"
              stroke="currentColor" stroke-width="2">
              <path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
            </svg>
          </button>
        </div>


        <!-- Mobile Menu Content -->
        <div class="flex flex-col text-left space-y-4 pt-3 px-6">
          <span @click="isOpen = false">
            <NuxtLink class="text-primary text-lg" to="/">Home</NuxtLink>
          </span>

          <span @click="isOpen = false">
            <NuxtLink class="text-primary text-lg" to="/">Reviews</NuxtLink>
          </span>

          <span @click="isOpen = false">
            <NuxtLink class="text-primary text-lg" to="/">Report</NuxtLink>
          </span>
        </div>
      </aside>
    </div>
    <!-- End of Mobile Navbar -->

  </div>
</template>


<script>
  export default {

    data() {
      return {
        isOpen: false,
      }
    },

    methods: {
      drawer() {
        this.isOpen = !this.isOpen
      }
    }

  }

</script>
