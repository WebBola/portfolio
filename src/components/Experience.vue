<script setup>
// const experiences = [
//   {
//     title: "Senior Frontend Developer",
//     company: "TechSoft Solutions",
//     location: "Toshkent, O'zbekiston",
//     period: "2023 - Hozir",
//     type: "To'liq vaqt",
//     description: "React va Next.js texnologiyalari bilan zamonaviy veb-ilovalar yaratish. Jamoa boshlig'i sifatida junior developerlarni o'qitish va mentorlik qilish.",
//     achievements: [
//       "15+ loyihani muvaffaqiyatli yakunlash",
//       "Kod sifatini 40% yaxshilash",
//       "Yangi texnologiyalarni joriy etish",
//       "Jamoa produktivligini 30% oshirish"
//     ],
//     technologies: ["React", "Next.js", "TypeScript", "Node.js", "AWS"]
//   },
//   {
//     title: "Frontend Developer",
//     company: "WebCraft Agency",
//     location: "Toshkent, O'zbekiston",
//     period: "2022 - 2023",
//     type: "To'liq vaqt",
//     description: "Turli mijozlar uchun responsive veb-saytlar va veb-ilovalar yaratish. UI/UX dizaynerlar bilan yaqin hamkorlik.",
//     achievements: [
//       "25+ veb-sayt yaratish",
//       "Mijozlar bilan to'g'ridan-to'g'ri ishlash",
//       "Mobile-first yondashuvni joriy etish",
//       "SEO optimizatsiya"
//     ],
//     technologies: ["React", "Vue.js", "Sass", "Webpack", "Figma"]
//   },
//   {
//     title: "Junior Web Developer",
//     company: "StartUp Hub",
//     location: "Toshkent, O'zbekiston",
//     period: "2021 - 2022",
//     type: "To'liq vaqt",
//     description: "Startaplar uchun MVP yaratish va prototiplash. Har xil texnologiyalar bilan tanishish va tajriba to'plash.",
//     achievements: [
//       "5+ startup loyihasi",
//       "Full-stack development",
//       "API integratsiya",
//       "Database design"
//     ],
//     technologies: ["JavaScript", "Node.js", "MongoDB", "Bootstrap"]
//   }
// ]

const education = [
    {
        degree: "Self-Study (Mustaqil o‘qish)",
        institution: "Uyda o‘qiganman",
        period: "2023 (1 yil)",
        description: "Frontend asoslarini mustaqil o‘rganganman. Amaliy loyihalar ustida ishlash orqali tajriba to‘plaganman."
    }
]
</script>

<template>
    <section id="experience" class="experience">
        <div class="container">
            <div class="text-center">
                <div class="badge">Tajriba</div>
                <h2 class="title">Ish Tajribam</h2>
                <p class="subtitle">
                    Men turli loyihalarda ishlash orqali tajriba to‘plaganman.
                </p>
            </div>

            <!-- Ish tajribasi -->
            <div class="section">
                <h3 class="subtitle-2">Ish Tajribasi</h3>
                <div v-if="experiences" v-for="(exp, index) in experiences" :key="index" class="card">
                    <div class="card-header">
                        <div>
                            <h4 class="card-title">{{ exp.title }}</h4>
                            <div class="meta">
                                <span>🏢 {{ exp.company }}</span>
                                <span>📍 {{ exp.location }}</span>
                                <span>📅 {{ exp.period }}</span>
                            </div>
                        </div>
                        <span class="badge outline">{{ exp.type }}</span>
                    </div>
                    <div class="card-body">
                        <p class="text">{{ exp.description }}</p>

                        <div>
                            <h4 class="mini-title">Asosiy Yutuqlar:</h4>
                            <ul class="achievements">
                                <li v-for="(ach, i) in exp.achievements" :key="i">
                                    <span class="dot"></span> {{ ach }}
                                </li>
                            </ul>
                        </div>

                        <div class="tech-list">
                            <span v-for="(tech, i) in exp.technologies" :key="i" class="badge small">
                                {{ tech }}
                            </span>
                        </div>
                    </div>
                </div>

                <div v-else>
                    <p>Xali biron bir kompaniyada ishlamaganman</p>
                </div>
            </div>

            <!-- Ta'lim -->
            <div class="section">
                <h3 class="subtitle-2">Ta'lim</h3>
                <div class="grid">
                    <div v-if="education" v-for="(edu, index) in education" :key="index" class="card">
                        <div class="card-header">
                            <h4 class="card-title">{{ edu.degree }}</h4>
                            <div class="meta">
                                <span>🏫 {{ edu.institution }}</span>
                                <span>📅 {{ edu.period }}</span>
                            </div>
                        </div>
                        <div class="card-body">
                            <p class="text">{{ edu.description }}</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<style scoped>
.experience {
    padding: 80px 20px;
    background: #f9fafb;
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
    border-radius: 8px;
    font-size: 14px;
    margin-bottom: 12px;
}

.badge.small {
    font-size: 12px;
    padding: 4px 8px;
}

.badge.outline {
    border: 1px solid #374151;
    background: transparent;
}

.title {
    font-size: 32px;
    font-weight: 400;
    margin-bottom: 16px;
}

.subtitle {
    font-size: 16px;
    color: #6b7280;
    max-width: 700px;
    margin: 0 auto;
}

.subtitle-2 {
    font-size: 24px;
    font-weight: 600;
    margin-bottom: 20px;
}

.section {
    margin-bottom: 60px;
}

.card {
    border: 1px solid #e5e7eb;
    border-radius: 12px;
    padding: 20px;
    margin-bottom: 20px;
    background: white;
    transition: box-shadow 0.3s;
}

.card:hover {
    box-shadow: 0 6px 20px rgba(0, 0, 0, 0.08);
}

.card-header {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 12px;
    margin-bottom: 16px;
}

.card-title {
    font-size: 20px;
    font-weight: bold;
    margin-bottom: 8px;
}

.meta {
    display: flex;
    flex-wrap: wrap;
    gap: 12px;
    font-size: 14px;
    color: #6b7280;
}

.card-body .text {
    font-size: 14px;
    color: #6b7280;
    margin-bottom: 16px;
}

.mini-title {
    font-weight: 600;
    margin-bottom: 8px;
}

.achievements {
    list-style: none;
    padding: 0;
    margin: 0 0 16px 0;
    display: grid;
    gap: 6px;
}

.achievements li {
    display: flex;
    align-items: center;
    font-size: 14px;
    color: #6b7280;
}

.dot {
    width: 6px;
    height: 6px;
    background: #2563eb;
    border-radius: 50%;
    margin-right: 8px;
}

.tech-list {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
}

.grid {
    display: grid;
    gap: 20px;
}

@media (min-width: 768px) {
    .grid {
        grid-template-columns: repeat(2, 1fr);
    }
}
</style>
