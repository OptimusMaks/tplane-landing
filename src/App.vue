<template>
  <div class="bg-gradient-to-b from-purple-700 to-black min-h-screen text-white pl-96 pr-96">
    <header class="w-full flex justify-between items-center px-6 py-4">
      <div class="flex items-center">
        <a href="#" class="mr-4">
          <img src="./img/icon-tg.svg" alt="">
        </a>
        <a href="#" class="mr-4">
            <img src="./img/icon-twitter.svg" alt="">
        </a>
        <a href="#" class="text-white hover:text-gray-400 transition-colors duration-300">News</a>
      </div>
      <div class="flex items-center">
        <img src="./img/Logo.svg" alt="" class="" />
      </div>
      <button class="bg-gradient-to-r from-[#8061FB] to-[#F48EE3] px-8 py-4 rounded-full hover:bg-gradient-to-r hover:from-[#F48EE3] hover:to-[#8061FB] transition-colors duration-300 font-bold">
        Play Now
      </button>
    </header>

    <section class="w-full max-w-5xl mx-auto">
      <h2 class="text-4xl font-semibold mb-6 text-center">Roadmap</h2>
      <ul class="space-y-4">
        <li class="bg-gray-800 p-4 rounded-lg shadow-md hover:scale-105 transition-transform duration-300">
          <span class="text-purple-400">March 2024</span>
          <div class="h-16 bg-gray-600 mt-2">
            <ul class="flex items-center justify-between h-full px-4">
              <li>Сделали игру</li>
              <li>Сделали обновления для майнинга</li>
              <li>Сделали возможность получать задания</li>
            </ul>
          </div>
        </li>
        <li class="bg-gray-800 p-4 rounded-lg shadow-md hover:scale-105 transition-transform duration-300">
          <span class="text-purple-400">April 2024</span>
          <div class="h-16 bg-gray-600 mt-2">
            <ul class="flex items-center justify-between h-full px-4">
              <li>Референтная система приглаcи друга</li>
              <li>Рейтинг пользователей</li>
            </ul>
          </div>
        </li>
        <li class="bg-gray-800 p-4 rounded-lg shadow-md hover:scale-105 transition-transform duration-300">
          <span class="text-purple-400">May 2024</span>
          <div class="h-16 bg-gray-600 mt-2">
            <!-- Placeholder for SVG: May 2024 -->
          </div>
        </li>
      </ul>
    </section>

    <footer class="mt-auto py-6 text-center">
      <p class="text-gray-400">Pavel Durov Approved It</p>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'App',
}
</script>

<style scoped>
/* Additional styles can be added here */
</style>
