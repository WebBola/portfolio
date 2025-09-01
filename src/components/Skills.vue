<script setup>
import { ref } from "vue"

const skillCategories = ref([
    {
        title: "Frontend Texnologiyalar",
        skills: [
            { name: "Vue.js", level: 75 },
            { name: "JavaScript", level: 80 },
            { name: "CSS", level: 85 },
            { name: "HTML", level: 90 }
        ]
    },
    {
        title: "Backend Texnologiyalar",
        skills: [
            { name: "Firebase (Auth, Firestore, Hosting)", level: 70 },
            { name: "REST API (asosiy tushunchalar)", level: 30 }
        ]
    },
    {
        title: "Asboblar va Platformalar",
        skills: [
            { name: "Git", level: 80 },
            { name: "Figma", level: 70 },
            { name: "VS Code", level: 95 }
        ]
    }
])

const frameworks = ref([
    "Vue.js", "JavaScript", "HTML", "CSS",
    "Firebase",
    "Bootstrap", "Git"
])
</script>

<template>
    <section id="skills" class="skills">
        <div class="skills-header">
            <span class="badge">Ko'nikmalar</span>
            <h2>Texnik Ko'nikmalarim</h2>
            <p>
                Men yosh va iqtidorli frontend dasturchiman. Asosan Vue.js, CSS va
                JavaScript texnologiyalari bilan ishlayman. Backend tarafida Firebase
                bilan ishlash tajribam bor (Auth, Firestore, Hosting). Doimiy ravishda
                yangi frameworklar va amaliy loyihalar orqali o‘zimni rivojlantirib
                boraman.
            </p>
        </div>

        <div class="categories">
            <div v-for="(category, index) in skillCategories" :key="index" class="card">
                <h3>{{ category.title }}</h3>
                <div v-for="(skill, i) in category.skills" :key="i" class="skill">
                    <div class="skill-header">
                        <span>{{ skill.name }}</span>
                        <span class="level">{{ skill.level }}%</span>
                    </div>
                    <div class="progress">
                        <div class="progress-bar" :style="{ width: skill.level + '%' }"></div>
                    </div>
                </div>
            </div>
        </div>

        <div class="frameworks">
            <h3>Ishlagan Texnologiyalarim</h3>
            <div class="framework-list">
                <span v-for="(fw, index) in frameworks" :key="index" class="badge outline">
                    {{ fw }}
                </span>
            </div>
        </div>
    </section>
</template>


<style scoped>
.skills {
    padding: 80px 20px;
    background: #f9fafb;
    max-width: 1200px;
    margin: auto;
}

.skills-header {
    text-align: center;
    margin-bottom: 50px;
}

.skills-header h2 {
    font-size: 28px;
    margin-bottom: 16px;
}

.skills-header p {
    color: #6b7280;
    max-width: 700px;
    margin: auto;
    font-size: 16px;
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

.badge.outline {
    background: transparent;
    border: 1px solid #d1d5db;
}

.categories {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 24px;
    margin-bottom: 60px;
}

.card {
    background: #fff;
    border: 1px solid #e5e7eb;
    border-radius: 8px;
    padding: 20px;
}

.card h3 {
    font-size: 18px;
    margin-bottom: 16px;
}

.skill {
    margin-bottom: 16px;
}

.skill-header {
    display: flex;
    justify-content: space-between;
    margin-bottom: 6px;
}

.level {
    color: #6b7280;
    font-size: 13px;
}

.progress {
    background: #e5e7eb;
    height: 8px;
    border-radius: 4px;
    overflow: hidden;
}

.progress-bar {
    background: black;
    height: 100%;
}

.frameworks {
    text-align: center;
}

.frameworks h3 {
    font-size: 22px;
    margin-bottom: 20px;
}

.framework-list {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 12px;
}
</style>
