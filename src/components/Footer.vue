<script setup>
import { ref } from "vue"

const currentYear = new Date().getFullYear()

const footerLinks = [
  {
    title: "Tezkor Havolalar",
    links: [
      { name: "Bosh sahifa", href: "#home" },
      { name: "Men haqimda", href: "#about" },
      { name: "Ko'nikmalar", href: "#skills" },
      { name: "Loyihalar", href: "#projects" }
    ]
  },
  {
    title: "Xizmatlar",
    links: [
      { name: "Frontend dasturlash", href: "#" },
      { name: "Backend (Firebase)", href: "#" },
      { name: "Fullstack loyihalar", href: "#" },
      { name: "Maslahat (Consulting)", href: "#" }
    ]
  },
  {
    title: "Bog'lanish",
    links: [
      { name: "webdasturchi2009@gmail.com", href: "mailto:webdasturchi2009@gmail.com" },
      { name: "+998 94 021 33 03", href: "tel:+998940213303" },
      { name: "Toshkent, O'zbekiston", href: "https://maps.google.com/?q=Tashkent" },
      { name: "Telegram", href: "https://t.me/behruz_dot" }
    ]
  }
]

const scrollToSection = (href) => {
  if (href.startsWith("#")) {
    const element = document.querySelector(href)
    if (element) {
      element.scrollIntoView({ behavior: "smooth" })
    }
  } else {
    window.open(href, "_blank")
  }
}
</script>

<template>
  <footer class="footer">
    <div class="container">
      <div class="grid">
        <!-- Logo and Description -->
        <div class="block">
          <h3 class="logo">Behruz</h3>
          <p class="desc">
            Frontend bo‘yicha tajribaga ega dasturchi. 
            Zamonaviy veb-saytlar va foydali loyihalar yarataman.
          </p>
          <div class="socials">
            <a href="https://github.com/WebBola" target="_blank" class="icon-btn">
              <img src="/icons/github.png" alt="GitHub" class="icon" />
            </a>
            <a href="https://t.me/behruz_dot" target="_blank" class="icon-btn">
              <img src="/icons/telegram.png" alt="Telegram" class="icon" />
            </a>
            <a href="https://www.instagram.com/dyrroth.n1/" target="_blank" class="icon-btn">
              <img src="/icons/instagram.png" alt="Instagram" class="icon" />
            </a>
          </div>
        </div>

        <!-- Footer Links -->
        <div v-for="(section, i) in footerLinks" :key="i" class="block">
          <h4 class="heading">{{ section.title }}</h4>
          <ul>
            <li v-for="(link, j) in section.links" :key="j">
              <button class="link" @click="scrollToSection(link.href)">
                {{ link.name }}
              </button>
            </li>
          </ul>
        </div>
      </div>

      <!-- Bottom Section -->
      <div class="bottom">
        <p>© {{ currentYear }} Behruz. Barcha huquqlar himoyalangan.</p>
        <div class="made">
          <span>Ishlab chiqildi</span>
          <span class="heart">❤️</span>
          <span>bilan O'zbekistonda</span>
        </div>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  background: #f9fafb;
  border-top: 1px solid #e5e7eb;
  padding: 60px 20px 20px;
}
.container {
  max-width: 1200px;
  margin: auto;
}
.grid {
  display: grid;
  gap: 24px;
  margin-bottom: 40px;
}
@media (min-width: 768px) {
  .grid {
    grid-template-columns: 1fr 1fr;
  }
}
@media (min-width: 1024px) {
  .grid {
    grid-template-columns: 1fr 1fr 1fr 1fr;
  }
}
.block {
  display: flex;
  flex-direction: column;
  gap: 12px;
}
.logo {
  font-size: 20px;
  font-weight: bold;
}
.desc {
  color: #6b7280;
  font-size: 14px;
}
.socials {
  display: flex;
  gap: 8px;
}
.icon-btn {
  border: 1px solid #d1d5db;
  border-radius: 6px;
  width: 36px;
  height: 36px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: white;
  cursor: pointer;
}
.icon-btn:hover {
  background: #f3f4f6;
}
.icon {
    height: 15px;
}
.heading {
  font-size: 16px;
  font-weight: 600;
  margin-bottom: 8px;
}
ul {
  list-style: none;
  padding: 0;
  margin: 0;
}
.link {
  color: #6b7280;
  font-size: 14px;
  background: none;
  border: none;
  padding: 0;
  cursor: pointer;
  text-align: left;
}
.link:hover {
  color: #111827;
}
.bottom {
  border-top: 1px solid #e5e7eb;
  padding-top: 20px;
  display: flex;
  flex-direction: column;
  gap: 12px;
  text-align: center;
  font-size: 14px;
  color: #6b7280;
}
@media (min-width: 768px) {
  .bottom {
    flex-direction: row;
    justify-content: space-between;
    text-align: left;
  }
}
.made {
  display: flex;
  align-items: center;
  gap: 6px;
}
.heart {
  color: red;
}
</style>
