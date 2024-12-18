<template>
    <div class="bg-black min-h-screen text-white">
        <!-- Шапка -->
        <header class="w-full p-4" :class="{ 'header-scrolled': isScrolled }">
            <div class="flex justify-between items-center max-w-6xl mx-auto">
                <div class="logo-animation">
                    <img src="./img/TANK-BANK.svg" alt="Tank Bank Logo" class="h-12" />
                </div>
                <button
                    @mouseover="handleButtonHover"
                    @mouseout="handleButtonLeave"
                    class="play-button bg-[#1A2F00] text-[#B1FF00] text-aw px-8 py-2 rounded relative overflow-hidden"
                >
                    <span class="relative z-10">Play</span>
                    <div class="button-glow"></div>
                </button>
            </div>
        </header>

        <main class="max-w-6xl mx-auto px-4 pt-8">
            <!-- Новогодний баннер -->
            <div class="mb-8 mr-3 hover:scale-105  transition-transform cursor-pointer flex items-center">
                <img src="./img/HAPPY-NY.png" alt="Happy New Year" class="" />

            </div>

            <!-- Снежинки -->
            <div v-if="showSnowfall" class="snowfall-container">
                <div v-for="n in 50" :key="n" class="snowflake" :style="getRandomSnowflakeStyle()"></div>
            </div>

            <!-- Главный заголовок -->
            <div class="text-center mb-8">
                <h1
                    class="text-2xl mb-4 title-animation"
                    :class="{ 'title-visible': titleVisible }"
                    v-intersect="handleTitleIntersect"
                >
                    Realtime 2D-shooter with
                    <span class="text-[#B1FF00] text-aw glow-text">real money</span>
                    withdrawal inside Telegram
                </h1>
                <div class="text-center">
                    <img src="./img/1.svg" alt="#1" class="h-8 mx-auto" />
                </div>
            </div>

            <!-- Секция с танком -->
            <div class="relative w-full aspect-video mb-12 tank-container" @mousemove="handleTankMovement" ref="tankContainer">
                <img src="./img/tank.png" alt="Tank" class="w-full h-full object-contain tank-element" :style="tankPosition" />
            </div>

            <!-- Кнопки функций -->
            <div class="grid grid-cols-3 gap-4 mb-16">
                <div v-for="(feature, index) in features" :key="feature.title"
                     :class="[
            'p-4 rounded transform -skew-x-12 feature-card',
            feature.highlighted
        ]"
                     :style="getFeatureDelay(index)"
                     @click="handleFeatureClick(feature)"
                >
                    <div class="transform skew-x-12 flex items-center justify-center">
                        <img :src="`${feature.icon}`" :alt="feature.title" class="mr-2 icon-pulse" />
                        <span class="font-bold">{{ feature.title }}</span>
                    </div>
                </div>
            </div>

            <!-- Дата выхода -->
            <div
                class="text-center mb-16 countdown-container"
                v-intersect="handleCountdownIntersect"
            >
                <div class="text-gray-400 mb-2">Release</div>
                <div class="text-3xl font-bold">
                    <span class="countdown-number">{{ countdownData.days }}</span> days
                    <span class="countdown-number">{{ countdownData.hours }}</span> hours
                    <span class="countdown-number">{{ countdownData.minutes }}</span> minutes
                </div>
            </div>

            <!-- Центры разработки -->
            <!-- Добавляем секцию Our Story после счетчика -->
            <div class="text-center mb-16">
                <div class="flex flex-col items-center justify-center">
                    <!-- Иконка и заголовок -->
                    <div class="mb-8">
                        <img src="./img/story-icon.svg" alt="Our Story" class="h-12 mx-auto mb-4" />
                        <div class="text-2xl font-bold">Our story</div>
                    </div>

                    <!-- Основной текст -->
                    <div class="max-w-3xl mx-auto space-y-6 text-center">
                        <p class="text-gray-300">
                            We started as a group of believers who shared a passion for games and technology.
                        </p>

                        <p class="text-gray-300">
                            Although life has taken us all over the world - from
                            <span class="text-[#B1FF00] text-aw">San Francisco to Singapore</span>, from
                            <span class="text-[#B1FF00] text-aw">Berlin to Tokyo</span> - our team and shared dream of creating something unique has only grown
                            <span class="text-[#B1FF00] text-aw">stronger</span>.
                        </p>

                        <p class="text-gray-300">
                            <span class="text-white font-bold">Tank Bank</span> the first game in its class, it's an embodiment of our shared idea of what modern games should look like:
                            <span class="text-[#B1FF00] text-aw">addictive gameplay</span>,
                            <span class="text-[#B1FF00] text-aw">fair economy</span> and a
                            <span class="text-[#B1FF00] text-aw">real community</span>.
                        </p>
                    </div>

                    <!-- Development Hubs -->
                    <div class="grid grid-cols-3 gap-8 w-full mt-12">
                        <div v-for="(hub, index) in developmentHubs" :key="hub.name"

                        >
                            <img :src="`${hub.icon}`" :alt="hub.name" class="mx-auto" />

                            <p class="text-gray-500">Development hub</p>
                        </div>
                    </div>
                </div>
            </div>
        </main>
    </div>
</template>

<script>
import pvpIcon from '/src/img/pvp.png'
import earnIcon from '/src/img/earn.png'
import matchIcon from '/src/img/match.png'
import americaIcon from '/src/img/america.png'
import europeIcon from '/src/img/europe.png'
import asiaIcon from '/src/img/asia.png'

export default {
    name: 'TankBankLanding',
    data() {
        return {
            isScrolled: false,
            showSnowfall: false,
            titleVisible: false,
            activeHub: null,
            tankPosition: {
                transform: 'translate(0px, 0px) rotate(0deg)'
            },
            countdownData: {
                days: 0,
                hours: 0,
                minutes: 0
            },
            features: [
                {
                    // title: 'PVP-Battles',
                    highlighted: true,
                    icon: pvpIcon
                },
                {
                    // title: 'Earn crypto',
                    highlighted: false,
                    icon: earnIcon
                },
                {
                    // title: 'Quick match',
                    highlighted: true,
                    icon: matchIcon
                }
            ],
            developmentHubs: [
                {
                    name: 'America',
                    icon: americaIcon
                },
                {
                    name: 'Europe',
                    icon: europeIcon
                },
                {
                    name: 'Asia',
                    icon: asiaIcon
                }
            ]
        }
    },
    mounted() {
        window.addEventListener('scroll', this.handleScroll)
        this.startCountdown()
    },
    methods: {
        handleScroll() {
            this.isScrolled = window.scrollY > 50
        },
        toggleSnowfall() {
            this.showSnowfall = !this.showSnowfall
        },
        getRandomSnowflakeStyle() {
            return {
                '--fall-duration': `${Math.random() * 3 + 2}s`,
                '--fall-delay': `${Math.random() * 2}s`,
                left: `${Math.random() * 100}%`
            }
        },
        handleTankMovement(e) {
            const container = this.$refs.tankContainer
            const rect = container.getBoundingClientRect()
            const x = e.clientX - rect.left
            const y = e.clientY - rect.top
            const rotateX = (y - rect.height / 2) * 0.1
            const rotateY = (x - rect.width / 2) * 0.1

            this.tankPosition = {
                transform: `translate(${rotateY * 0.5}px, ${rotateX * 0.5}px) rotate(${rotateY * 0.02}deg)`
            }
        },
        handleFeatureClick(feature) {
            // Добавляем эффект пульсации при клике
            const elements = document.querySelectorAll('.feature-card')
            elements.forEach(el => el.classList.add('feature-pulse'))
            setTimeout(() => {
                elements.forEach(el => el.classList.remove('feature-pulse'))
            }, 500)
        },
        handleButtonHover() {
            // Добавляем эффект свечения при наведении
            const button = document.querySelector('.play-button')
            button.classList.add('button-hover')
        },
        handleButtonLeave() {
            const button = document.querySelector('.play-button')
            button.classList.remove('button-hover')
        },
        getFeatureDelay(index) {
            return {
                animationDelay: `${index * 0.2}s`
            }
        },
        startCountdown() {
            const targetDate = new Date('2024-12-31').getTime()

            setInterval(() => {
                const now = new Date().getTime()
                const distance = targetDate - now

                this.countdownData = {
                    days: Math.floor(distance / (1000 * 60 * 60 * 24)),
                    hours: Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60)),
                    minutes: Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60))
                }
            }, 1000)
        },
        handleTitleIntersect(entries) {
            if (entries[0].isIntersecting) {
                this.titleVisible = true
            }
        },
        handleCountdownIntersect(entries) {
            if (entries[0].isIntersecting) {
                entries[0].target.classList.add('countdown-visible')
            }
        }
    },
    beforeDestroy() {
        window.removeEventListener('scroll', this.handleScroll)
    }
}
</script>

<style scoped>
/* Базовые анимации */
.transform {
    transition: all 0.3s ease;
}

/* Анимация логотипа */
.logo-animation {
    animation: logoFloat 3s ease-in-out infinite;
}

@keyframes logoFloat {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-10px); }
}

/* Анимация заголовка */
.title-animation {
    opacity: 0;
    transform: translateY(20px);
    transition: all 0.8s ease;
}

.title-visible {
    opacity: 1;
    transform: translateY(0);
}

/* Эффект свечения текста */
.glow-text {
    text-shadow: 0 0 10px rgba(177, 255, 0, 0.5);
    animation: textPulse 2s ease-in-out infinite;
}

@keyframes textPulse {
    0%, 100% { text-shadow: 0 0 10px rgba(177, 255, 0, 0.5); }
    50% { text-shadow: 0 0 20px rgba(177, 255, 0, 0.8); }
}

/* Анимация кнопки Play */
.play-button {
    transition: all 0.3s ease;
}

.button-hover {
    transform: scale(1.05);
    box-shadow: 0 0 20px rgba(177, 255, 0, 0.3);
}

.button-glow {
    position: absolute;
    top: -50%;
    left: -50%;
    width: 200%;
    height: 200%;
    background: linear-gradient(45deg, transparent, rgba(177, 255, 0, 0.1), transparent);
    transform: rotate(45deg);
    animation: buttonGlow 2s linear infinite;
}

@keyframes buttonGlow {
    0% { transform: translateX(-100%) rotate(45deg); }
    100% { transform: translateX(100%) rotate(45deg); }
}

/* Анимация карточек функций */
.feature-card {
    animation: featureAppear 0.5s ease forwards;
    opacity: 0;
    transform: translateY(20px) skewX(-12deg);
}

@keyframes featureAppear {
    to {
        opacity: 1;
        transform: translateY(0) skewX(-12deg);
    }
}

.feature-pulse {
    animation: pulse 0.5s ease;
}

@keyframes pulse {
    0%, 100% { transform: scale(1) skewX(-12deg); }
    50% { transform: scale(1.05) skewX(-12deg); }
}

/* Анимация иконок */
.icon-pulse {
    animation: iconPulse 2s ease-in-out infinite;
}

@keyframes iconPulse {
    0%, 100% { transform: scale(1); }
    50% { transform: scale(1.2); }
}

/* Анимация хабов разработки */
.hub-card {
    transition: all 0.3s ease;
}

.hub-active {
    transform: translateY(-10px);
    box-shadow: 0 10px 20px rgba(177, 255, 0, 0.2);
}

/* Анимация снежинок */
.snowfall-container {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    pointer-events: none;
    z-index: 100;
}

.snowflake {
    position: absolute;
    width: 5px;
    height: 5px;
    background: white;
    border-radius: 50%;
    animation: snowfall var(--fall-duration) linear infinite;
    animation-delay: var(--fall-delay);
    opacity: 0.7;
}

@keyframes snowfall {
    0% {
        transform: translateY(-100px);
    }
    100% {
        transform: translateY(100vh);
    }
}

/* Анимация счётчика */
.countdown-container {
    opacity: 0;
    transform: translateY(20px);
    transition: all 0.8s ease;
}

.countdown-visible {
    opacity: 1;
    transform: translateY(0);
}

.countdown-number {
    display: inline-block;
    background: rgba(177, 255, 0, 0.1);
    padding: 0.5rem 1rem;
    border-radius: 0.5rem;
    margin: 0 0.5rem;
    min-width: 80px;
    animation: numberPulse 1s ease-in-out infinite;
}

@keyframes numberPulse {
    0%, 100% { transform: scale(1); }
    50% { transform: scale(1.05); }
}

/* Анимация прокрутки шапки */
.header-scrolled {
    background: rgba(0, 0, 0, 0.8);
    backdrop-filter: blur(10px);
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    z-index: 1000;
    animation: headerSlideDown 0.5s ease;
}

@keyframes headerSlideDown {
    from {
        transform: translateY(-100%);
    }
    to {
        transform: translateY(0);
    }
}

/* Анимация танка */
.tank-container {
    perspective: 1000px;
}

.tank-element {
    transition: transform 0.1s ease;
    transform-style: preserve-3d;
}

.text-aw {
    transition: color 0.3s ease;
}

.text-aw:hover {
                   text-shadow: 0 0 10px rgba(177, 255, 0, 0.5);
               }

/* Анимация появления текста */
p {
    opacity: 0;
    transform: translateY(20px);
    animation: fadeIn 0.8s ease forwards;
}

@keyframes fadeIn {
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

/* Добавляем задержку для каждого параграфа */
p:nth-child(1) { animation-delay: 0.2s; }
p:nth-child(2) { animation-delay: 0.4s; }
p:nth-child(3) { animation-delay: 0.6s; }
</style>