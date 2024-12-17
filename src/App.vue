<template>
    <div class="bg-black min-h-screen text-white relative overflow-hidden">
        <!-- Header -->
        <header class="w-full flex justify-between items-center py-6 px-8">
            <div class="flex items-center space-x-4">
                <a href="#" class="hover:opacity-80">
                    <!-- <img src="@/assets/telegram-icon.svg" alt="Telegram" class="w-6 h-6" /> -->
                </a>
                <a href="#" class="hover:opacity-80">
                    <!-- <img src="@/assets/twitter-icon.svg" alt="Twitter" class="w-6 h-6" /> -->
                </a>
                <a href="#" class="text-[#B1FF00] hover:opacity-80 highlight-text">News</a>
            </div>

            <div class="flex-shrink-0">
                <!-- <img src="@/assets/tank-bank-logo.svg" alt="Tank Bank" class="h-12" /> -->
            </div>

            <button class="bg-[#B1FF00] text-black px-8 py-3 rounded-full font-bold hover:bg-opacity-80 transition-all glow-button">
                Play Now
            </button>
        </header>

        <!-- Hero Section -->
        <section class="relative pt-20 pb-32 text-center px-4">
            <div class="max-w-4xl mx-auto">
                <h1 class="text-6xl font-bold mb-6">
                    <span class="text-[#B1FF00] highlight-text">TANK</span> BATTLE
                </h1>
                <p class="text-xl mb-12 text-gray-300">
                    [Your text will be here]
                </p>
                <button class="bg-[#B1FF00] text-black px-12 py-4 rounded-full font-bold text-xl hover:bg-opacity-80 transition-all glow-button">
                    Start Game
                </button>
            </div>
        </section>

        <!-- Features -->
        <section class="py-20 bg-black/50">
            <div class="max-w-6xl mx-auto px-4 grid grid-cols-1 md:grid-cols-3 gap-8">
                <div v-for="feature in features" :key="feature"
                     class="text-center p-8 border border-[#B1FF00] rounded-lg feature-card">
                    <h3 class="text-[#B1FF00] text-2xl font-bold mb-4">{{ feature }}</h3>
                </div>
            </div>
        </section>

        <!-- Roadmap -->
        <section class="py-20 px-4">
            <div class="max-w-6xl mx-auto">
                <h2 class="text-4xl font-bold text-center mb-16">
                    <span class="text-[#B1FF00] highlight-text">Road</span>map
                </h2>
                <div class="space-y-8">
                    <div v-for="(phase, index) in roadmap" :key="index"
                         class="border border-[#B1FF00] rounded-lg p-6 hover:bg-[#B1FF00]/5 transition-all feature-card">
                        <h3 class="text-[#B1FF00] text-2xl font-bold mb-4">{{ phase.date }}</h3>
                        <ul class="space-y-2">
                            <li v-for="(item, itemIndex) in phase.items" :key="itemIndex"
                                class="flex items-start">
                                <span class="w-2 h-2 bg-[#B1FF00] rounded-full mr-4 mt-2 flex-shrink-0"></span>
                                <span>{{ item }}</span>
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
        </section>

        <!-- Team Section -->
        <section class="py-20 px-4">
            <div class="max-w-6xl mx-auto">
                <h2 class="text-4xl font-bold text-center mb-16">
                    <span class="text-[#B1FF00] highlight-text">Our</span> Story
                </h2>
                <div class="text-center max-w-4xl mx-auto mb-16">
                    <p class="text-xl leading-relaxed mb-8">
                        Мы начали как группа школьных друзей, разделяющих страсть к играм и технологиям. Несмотря на то, что жизнь разбросала нас по разным уголкам мира - от Сан-Франциско до Сингапура, от Берлина до Токио - наша дружба и общая мечта создать что-то уникальное только окрепли.
                    </p>
                    <p class="text-xl leading-relaxed">
                        Tank Bank - это не просто игра, это воплощение нашей общей идеи о том, как должны выглядеть современные игры: захватывающий геймплей, честная экономика и настоящее коммьюнити.
                    </p>
                </div>
                <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                    <div v-for="location in locations" :key="location"
                         class="text-center p-8 border border-[#B1FF00] rounded-lg feature-card">
                        <h3 class="text-[#B1FF00] text-2xl font-bold mb-4">{{ location }}</h3>
                        <p class="text-gray-400">Development Hub</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Wallet Section -->
        <section class="py-20 bg-black/50">
            <div class="max-w-6xl mx-auto px-4">
                <div class="grid grid-cols-1 md:grid-cols-2 gap-12 items-center">
                    <div>
                        <h2 class="text-4xl font-bold mb-6">
                            <span class="text-[#B1FF00] highlight-text">Crypto</span> Wallet
                        </h2>
                        <p class="text-xl mb-8 text-gray-300">
                            Secure crypto transactions for in-game operations
                        </p>
                        <div class="flex flex-wrap gap-4">
                            <div v-for="crypto in cryptocurrencies" :key="crypto"
                                 class="bg-black/80 p-4 rounded-lg feature-card">
                                <span class="text-[#B1FF00]">{{ crypto }}</span>
                            </div>
                        </div>
                    </div>
                    <div class="relative">
                        <div class="aspect-square bg-[#B1FF00]/10 rounded-lg feature-card"></div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Footer -->
        <footer class="py-8 border-t border-[#B1FF00]/20">
            <div class="max-w-6xl mx-auto px-4 flex justify-between items-center">
                <div class="text-sm text-gray-500">© 2024 Tank Bank. All rights reserved.</div>
                <div class="flex space-x-4">
                    <a href="#" class="text-[#B1FF00] hover:opacity-80 highlight-text">Terms</a>
                    <a href="#" class="text-[#B1FF00] hover:opacity-80 highlight-text">Privacy</a>
                </div>
            </div>
        </footer>
    </div>
</template>

<script>
export default {
    name: 'TankBankLanding',
    data() {
        return {
            features: ['PVP Battles', 'Earn Crypto', 'Weekly Tournaments'],
            cryptocurrencies: ['BTC', 'ETH', 'USDT', 'BNB'],
            locations: ['Americas', 'Europe', 'Asia'],
            roadmap: [
                {
                    date: 'December 2024',
                    items: [
                        'Запуск альфа-версии игры Tank Bank',
                        'Базовая механика танковых сражений',
                        'Интеграция криптокошелька'
                    ]
                },
                {
                    date: 'January 2025',
                    items: [
                        'Система матчмейкинга',
                        'Рейтинговые бои',
                        'Система достижений'
                    ]
                },
                {
                    date: 'February 2025',
                    items: [
                        'Турнирная система',
                        'Внутриигровой маркетплейс',
                        'Система наград за активность'
                    ]
                },
                {
                    date: 'March 2025',
                    items: [
                        'Клановая система',
                        'Специальные события',
                        'Расширенная система прогрессии'
                    ]
                }
            ]
        }
    }
}
</script>

<style scoped>
/* Анимации для появления элементов */
.fade-enter-active,
.fade-leave-active {
    transition: opacity 0.5s ease;
}

.fade-enter-from,
.fade-leave-to {
    opacity: 0;
}

/* Анимация для кнопок */
.glow-button {
    position: relative;
    overflow: hidden;
}

.glow-button::after {
    content: '';
    position: absolute;
    top: -50%;
    left: -50%;
    width: 200%;
    height: 200%;
    background: linear-gradient(
        45deg,
        transparent,
        rgba(177, 255, 0, 0.1),
        transparent
    );
    transform: rotate(45deg);
    animation: glow 3s linear infinite;
}

@keyframes glow {
    0% { transform: translateX(-100%) rotate(45deg); }
    100% { transform: translateX(100%) rotate(45deg); }
}

/* Анимация для карточек */
.feature-card {
    transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.feature-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 10px 20px rgba(177, 255, 0, 0.1);
}

/* Анимация для текста */
.highlight-text {
    position: relative;
    display: inline-block;
}

.highlight-text::after {
    content: '';
    position: absolute;
    width: 0;
    height: 2px;
    bottom: 0;
    left: 0;
    background-color: #B1FF00;
    transition: width 0.3s ease;
}

.highlight-text:hover::after {
    width: 100%;
}
</style>