<script setup>
import { ref } from "vue"

// Ikonlarni o'zimiz emoji yoki SVG bilan almashtiramiz
const features = ref([
  {
    icon: "/icons/code.png",
    title: "Dasturlash",
    description: "Modern texnologiyalar va eng yaxshi amaliyotlar bilan ishlash"
  },
  {
    icon: "/icons/paint.png",
    title: "Dizayn",
    description: "Foydalanuvchilar uchun qulay va chiroyli interfeys yaratish"
  },
  {
    icon: "/icons/flash.png",
    title: "Optimizatsiya",
    description: "Tez va samarali veb-ilovalar yaratish"
  },
  {
    icon: "/icons/people.png",
    title: "Hamkorlik",
    description: "Jamoa bilan ishlash va loyihalarni muvaffaqiyatli bajarish"
  }
])
</script>

<template>
  <section id="about" class="about">
    <div class="about-header">
      <span class="badge">Men haqimda</span>
      <h2>Dasturlash - bu mening ehtirosim</h2>
      <p>
        Men 2 yildan ortiq vaqt davomida veb-dasturlash sohasida ishlayman. 
        Zamonaviy texnologiyalar va eng yaxshi amaliyotlardan foydalanib, 
        foydalanuvchilar uchun qulay va chiroyli veb-saytlar yarataman.
      </p>
    </div>

    <div class="features">
      <div v-for="(feature, index) in features" :key="index" class="card">
        <div class="box"><img :src="feature.icon" class="icon" alt=""></div>
        <h3>{{ feature.title }}</h3>
        <p>{{ feature.description }}</p>
      </div>
    </div>

    <div class="details">
      <div class="details-text">
        <h3>Mening yo'lim</h3>
        <p>
          Dasturlash bilan tanishganimdan beri, men doimo yangi texnologiyalarni 
          o'rganish va o'z bilimlarimni rivojlantirishga intildim. Har bir loyiha 
          menga yangi tajriba va bilim beradi.
        </p>
        <p>
          Men nafaqat kod yozaman, balki mijozlar bilan yaqin hamkorlik qilib, 
          ularning ehtiyojlarini to'liq tushunishga harakat qilaman. Bu orqali 
          eng yaxshi natijaga erishaman.
        </p>
        <p>
          Maqsadim - har bir loyihani yuqori sifat va professional darajada 
          bajarish, mijozlarning kutganidan ham yaxshi natija berish.
        </p>
      </div>

      <div class="stats">
        <div class="stat-card">
          <div class="number">0</div>
          <p>Bajarilgan loyihalar</p>
        </div>
        <div class="stat-card">
          <div class="number">1</div>
          <p>Xursand mijozlar</p>
        </div>
        <div class="stat-card">
          <div class="number">2+</div>
          <p>Yillik tajriba</p>
        </div>
        <div class="stat-card">
          <div class="number">24/7</div>
          <p>Qo'llab-quvvatlash</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about {
  padding: 80px 20px;
  max-width: 1300px;
  margin: auto;
}
.about-header {
  text-align: center;
  margin-bottom: 60px;
}
.badge {
  display: inline-block;
  background: #e5e7eb;
  color: #374151;
  padding: 6px 12px;
  border-radius: 6px;
  margin-bottom: 16px;
  font-size: 14px;
}
.about-header h2 {
  font-size: 28px;
  font-weight: 500;
  margin-bottom: 16px;
}
.about-header p {
  max-width: 700px;
  margin: auto;
  color: #6b7280;
  font-size: 15px;
}
.features {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 20px;
  margin-bottom: 60px;
}
.card {
  text-align: center;
  padding: 20px;
  border: 1px solid #e5e7eb;
  border-radius: 8px;
  background: #fff;
}
.icon {
  font-size: 28px;
  margin-bottom: 12px;
}
.details {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 40px;
  align-items: start;
}
.details h3 {
  font-size: 22px;
  margin-bottom: 16px;
}
.details p {
  color: #6b7280;
  margin-bottom: 12px;
}
.stats {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 20px;
}
.stat-card {
  text-align: center;
  padding: 20px;
  border: 1px solid #e5e7eb;
  border-radius: 8px;
  background: #fff;
}

.card h3{
    font-size: 18px;
    font-weight: 500;
}

.card p{
    font-size: 14px;
    font-weight: 350;
    padding-top: 10px;
}
.number {
  font-size: 24px;
  font-weight: bold;
  margin-bottom: 6px;
}
.box{
    width: 40px;
    height: 40px;
    margin: 0 auto;
}

.box .icon {
    height: 30px;
}

@media (max-width: 768px) {
  .details {
    grid-template-columns: 1fr;
  }
}
</style>
