<template>
  <div id="app" class="bg-[#0A0A1E] min-h-screen text-white px-4 md:px-24 lg:px-96 relative overflow-hidden">
    <!-- Фоновые SVG -->
    <div class="absolute left-[0px] top-[550px] -translate-y-1/2 md:opacity-100 opacity-50">
      <img src="./img/Ellipse23.svg" alt="Левый эллипс SVG" />
    </div>
    <div class="absolute right-0 top-0 md:opacity-100 opacity-50">
      <img src="./img/Ellipse24.svg" alt="Верхний правый эллипс SVG" />
    </div>
    <div class="absolute right-0 bottom-0 md:opacity-100 opacity-50">
      <img src="./img/Ellipse25.svg" alt="Нижний правый эллипс SVG" />
    </div>
    <div class="absolute left-[500px] top-24">
      <img src="./img/Planes.svg" alt="SVG самолетиков" class="w-auto h-auto" />
    </div>
    <div class="absolute left-[350px] top-28">
      <img src="./img/Coins.svg" alt="SVG монет" class="w-auto h-auto" />
    </div>

    <header class="w-full flex justify-between items-center py-4">
      <div class="flex items-center space-x-2 md:space-x-4">
        <a href="#"><img src="./img/icon-tg.svg" alt="Telegram" class="w-6 h-6 md:w-auto md:h-auto" /></a>
        <a href="#"><img src="./img/icon-twitter.svg" alt="Twitter" class="w-6 h-6 md:w-auto md:h-auto" /></a>
        <a href="#" class="text-white hover:text-gray-400 transition-colors duration-300 text-sm md:text-base">News</a>
      </div>
      <div><img src="./img/Logo.svg" alt="Логотип" class="w-24 md:w-auto" /></div>
      <button class="bg-gradient-to-r from-[#8061FB] to-[#F48EE3] w-[100px] h-[40px] md:w-[140px] md:h-[58px] rounded-full hover:bg-gradient-to-r hover:from-[#F48EE3] hover:to-[#8061FB] transition-colors duration-300 font-bold text-sm md:text-base">
        Play now
      </button>
    </header>

    <section class="w-full max-w-5xl mx-auto text-center mt-24">
      <h2 class="text-5xl md:text-7xl font-semibold mb-5">Lorem ipsum dolor<br>sit amet</h2>
      <p class="text-lg md:text-xl mb-7">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Deserunt dignissimos reiciendis<br class="hidden md:inline">saepe. Cumque eaque et ipsum maiores?</p>
      <button class="bg-gradient-to-r from-[#8061FB] to-[#F48EE3] w-[200px] h-[60px] md:w-[294px] md:h-[94px] rounded-full hover:bg-gradient-to-r hover:from-[#F48EE3] hover:to-[#8061FB] transition-colors duration-700 font-bold text-xl md:text-3xl">
        Play now
      </button>
    </section>

    <section class="w-full max-w-5xl mx-auto mt-32">
      <h2 class="text-6xl font-semibold mb-6 text-center hidden md:block">Дорожная карта</h2>
      <p class="text-center mb-8 text-xl hidden md:block">Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
      <ul class="space-y-4">
        <li v-for="(phase, index) in roadmap" :key="index" class="bg-[#1A1A31] p-6 rounded-2xl shadow-lg hover:scale-105 transition-transform duration-300 border-2 border-[#B061FB] flex flex-col sm:flex-row">
          <h3 class="text-purple-400 text-2xl w-full sm:w-48 flex-shrink-0 mb-4 sm:mb-0">{{ phase.date }}</h3>
          <ul class="space-y-2 flex-grow sm:ml-80">
            <li v-for="(item, itemIndex) in phase.items" :key="itemIndex" class="flex items-start">
              <span class="w-2 h-2 bg-purple-400 rounded-full mr-4 mt-2 flex-shrink-0"></span>
              <span>{{ item }}</span>
            </li>
          </ul>
        </li>
      </ul>
    </section>

    <section class="w-full max-w-5xl mx-auto mt-32">
      <div class="max-w-7xl mx-auto flex flex-col md:flex-row items-center text-center md:text-left">
        <div class="md:w-1/2 z-10">
          <h2 class="text-4xl md:text-6xl font-bold mb-4">Павел Дуров одобрил это</h2>
          <p class="text-lg mb-8 text-gray-300">Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
          <button class="mb-8 md:mb-32 bg-gradient-to-r from-[#8061FB] to-[#F48EE3] w-[200px] h-[60px] md:w-[294px] md:h-[94px] rounded-full hover:bg-gradient-to-r hover:from-[#F48EE3] hover:to-[#8061FB] transition-colors duration-700 font-bold text-xl md:text-3xl">
            Play now
          </button>
        </div>
        <div class="md:w-1/2 mt-10 md:mt-0 relative mb-32 flex justify-center">
          <img src="./img/Durov.svg" alt="Павел Дуров" class="w-full h-auto max-w-md">
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