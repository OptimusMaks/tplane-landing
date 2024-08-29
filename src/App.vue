<template>
  <div class="bg-[#0A0A1E] min-h-screen text-white px-4 md:px-24 lg:px-96">
    <header class="w-full flex justify-between items-center py-4">
      <div class="flex items-center space-x-4">
        <a href="#"><img src="./img/icon-tg.svg" alt="Telegram" /></a>
        <a href="#"><img src="./img/icon-twitter.svg" alt="Twitter" /></a>
        <a href="#" class="text-white hover:text-gray-400 transition-colors duration-300">News</a>
      </div>
      <div><img src="./img/Logo.svg" alt="Logo" /></div>
      <button class="bg-gradient-to-r from-[#8061FB] to-[#F48EE3] w-[140px] h-[58px] rounded-full hover:bg-gradient-to-r hover:from-[#F48EE3] hover:to-[#8061FB] transition-colors duration-300 font-bold">
        Play Now
      </button>
    </header>

    <section class="w-full max-w-5xl mx-auto text-center mt-24">
      <h2 class="text-5xl md:text-7xl font-semibold mb-5">Lorem ipsum dolor sit amet</h2>
      <p class="text-lg md:text-xl mb-7">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Deserunt dignissimos reiciendis saepe. Cumque eaque et ipsum maiores?</p>
      <button class="bg-gradient-to-r from-[#8061FB] to-[#F48EE3] w-[294px] h-[94px] rounded-full hover:bg-gradient-to-r hover:from-[#F48EE3] hover:to-[#8061FB] transition-colors duration-700 font-bold text-3xl">
        Play Now
      </button>
    </section>
    <section class="w-full max-w-5xl mx-auto mt-32">
      <h2 class="text-6xl font-semibold mb-6 text-center">Roadmap</h2>
      <p class="text-center mb-8 text-xl">Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
      <ul class="space-y-4">
        <li v-for="(phase, index) in roadmap" :key="index" class="bg-[#1A1A31] p-6 rounded-2xl shadow-lg hover:scale-105 transition-transform duration-300 border-2 border-[#B061FB] flex">
          <h3 class="text-purple-400 text-2xl w-48 flex-shrink-0">{{ phase.date }}</h3>
          <ul class="space-y-2 flex-grow ml-80">
            <li v-for="(item, itemIndex) in phase.items" :key="itemIndex" class="flex items-start">
              <span class="w-2 h-2 bg-purple-400 rounded-full mr-4 mt-2 flex-shrink-0"></span>
              <span>{{ item }}</span>
            </li>
          </ul>
        </li>
      </ul>
    </section>

    <section class="w-full max-w-5xl mx-auto mt-32">
    <div class="max-w-7xl mx-auto flex flex-col md:flex-row items-center">
      <div class="md:w-1/2 z-10">
        <h2 class="text-4xl md:text-6xl font-bold mb-4">Pavel Durov Approved It</h2>
        <p class="text-lg mb-8 text-gray-300">Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
        <button class="mb-32 bg-gradient-to-r from-[#8061FB] to-[#F48EE3] w-[294px] h-[94px] rounded-full hover:bg-gradient-to-r hover:from-[#F48EE3] hover:to-[#8061FB] transition-colors duration-700 font-bold text-3xl">
          Play Now
        </button>
      </div>
      <div class="md:w-1/2 mt-10 md:mt-0 relative mb-32">
          <img src="./img/Durov.svg" alt="">
      </div>
    </div>
    </section>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      roadmap: [
        {
          date: 'March 2024',
          items: [
            'Сделали игру',
            'Сделали обновления для майнинга',
            'Сделали возможность получать задания'
          ]
        },
        {
          date: 'April 2024',
          items: [
            'Реферальная система пригласи друга',
            'Рейтинг пользователей',
            'Ежедневные награды'
          ]
        },
        {
          date: 'May 2024',
          items: [
            'Специальные карточки',
            'Размер дропа будет зависить от позиции в рейтинге',
            'TGE'
          ]
        },
        {
          date: 'March 2024',
          items: [
            'Виртуальная валюта + $HMSTR реальная валюта',
            'Повышение стоимости токена',
            'Запуск первого сезона'
          ]
        },
        {
          date: 'April 2024',
          items: [
            'Боевой отряд',
            'Персонажи и скины',
            'Мероприятия ограниченные по времени',
            'Ивенты'
          ]
        },
        {
          date: 'May 2024',
          items: [
            'Специальные карточки',
            'Размер дропа будет зависить от позиции в рейтинге',
            'TGE'
          ]
        }
      ]
    }
  }
}
</script>

<style scoped>
/* Additional styles can be added here if needed */
</style>