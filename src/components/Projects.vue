<script setup>
const projects = [
    {
        title: "PowerClick",
        description: "Oddiy va qiziqarli klikker o‘yini. Foydalanuvchilar klik qilish orqali ball to‘plashadi, upgrade’lar orqali o‘yinni tezlashtirish mumkin.",
        image: "/images/pc_anime_rise.png",
        technologies: ["Vue.js", "CSS", "Firebase"],
        liveUrl: "https://pc-anime-rise.netlify.app/",
        githubUrl: "https://github.com/WebBola/PowerClick-Anime-Rise"
    },
]
</script>

<template>
    <section id="projects" class="projects">
        <div class="container">
            <div class="text-center">
                <div class="badge">Loyihalar</div>
                <h2 class="title">Mening Ishlarim</h2>
                <p class="subtitle">
                    Men Vue.js va Firebase asosida bir nechta amaliy loyihalar qilganman.
                    Quyida ularning ayrimlarini ko‘rishingiz mumkin.
                </p>
            </div>

            <div class="grid">
                <div v-for="(project, index) in projects" :key="index" class="card">
                    <div class="card-img">
                        <img :src="project.image" :alt="project.title" />
                    </div>
                    <div class="card-body">
                        <h3 class="card-title">{{ project.title }}</h3>
                        <p class="card-text">{{ project.description }}</p>

                        <div class="tech-list">
                            <span v-for="(tech, i) in project.technologies" :key="i" class="badge small">
                                {{ tech }}
                            </span>
                        </div>

                        <div class="card-actions">
                            <!-- Asosiy qora button -->
                            <a :href="project.liveUrl" target="_blank" class="btn primary">
                                <span class="icon">↗</span>
                                Ko‘rish
                            </a>
                            <!-- Faqat icon button -->
                            <a :href="project.githubUrl" target="_blank" class="btn icon">
                                <img src="/icons/github.png" alt="">
                            </a>
                        </div>
                    </div>
                </div>
            </div>

            <div class="text-center">
                <a href="https://github.com/WebBola" target="_blank" class="btn outline large"> <img src="/icons/github.png"
                        alt=""> GitHub'da Ko‘proq Ko‘rish</a>
            </div>
        </div>
    </section>
</template>

<style scoped>
.projects {
    padding: 80px 20px;
}

.container {
    max-width: 1200px;
    margin: auto;
}

.text-center {
    text-align: center;
    margin-bottom: 40px;
}

.badge {
  display: inline-block;
    background: #e5e7eb;
    color: #374151;
    padding: 6px 12px;
    margin-bottom: 20px;
    border-radius: 6px;
    font-size: 14px;
}

.badge.small {
    font-size: 12px;
    padding: 2px 8px;
}

.title {
    font-size: 32px;
    margin-bottom: 16px;
}

.subtitle {
    font-size: 17px;
    color: #6b7280;
    max-width: 700px;
    margin: 0 auto;
}

.grid {
    display: grid;
    grid-template-columns: 1fr;
    gap: 24px;
    margin-bottom: 40px;
}

@media (min-width: 768px) {
    .grid {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (min-width: 1024px) {
    .grid {
        grid-template-columns: repeat(3, 1fr);
    }
}

.card {
    border: 1px solid #e5e7eb;
    border-radius: 12px;
    overflow: hidden;
    transition: all 0.3s;
    background: white;
}

.card:hover {
    box-shadow: 0 6px 20px rgba(0, 0, 0, 0.08);
    border-color: #111827;
}

.card-img {
    aspect-ratio: 16 / 9;
    overflow: hidden;
}

.card-img img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: transform .3s;
}

.card:hover .card-img img {
    transform: scale(1.05);
}

.card-body {
    padding: 16px;
}

.card-title {
    font-size: 20px;
    font-weight: bold;
    margin-bottom: 8px;
}

.card-text {
    font-size: 14px;
    color: #6b7280;
    margin-bottom: 12px;
}

.tech-list {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
    margin-bottom: 12px;
}

.card-actions {
    display: flex;
    gap: 8px;
    align-items: center;
}

/* 🔘 Buttonlar */
.btn {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 6px;
    border-radius: 8px;
    font-size: 14px;
    font-weight: 500;
    text-decoration: none;
    transition: all 0.2s ease;
    cursor: pointer;
}

/* qora uzun button */
.btn.primary {
    flex: 1;
    background: #0a0a1a;
    color: #fff;
    padding: 5px 16px;
}

.btn.primary:hover {
    background: #000;
    box-shadow: 0 2px 6px rgba(0, 0, 0, 0.25);
}

/* faqat iconli tugma */
.btn.icon {
    background: #fff;
    border: 1px solid #e5e7eb;
    padding: 5px 10px;
    border-radius: 8px;
    font-size: 16px;
    color: #111827;
}

.btn.icon:hover {
    background: #f9fafb;
    border-color: #111827;
}

.btn img {
    height: 18px;
}

/* outline */
.btn .outline {
    border: 1px solid #111827;
    color: #000000;
    padding: 5px 16px;
}

.btn.outline:hover {
    background: #00000046;
}

/* katta button */
.btn.large {
    font-size: 13px;
    padding: 7px 15px;
    color: #000;
    font-weight: 400;
    border: 1px solid #00000061;
}
</style>
