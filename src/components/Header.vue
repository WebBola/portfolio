<script setup>
import { ref } from "vue"

const isMenuOpen = ref(false)

const navItems = [
  { name: "Bosh sahifa", href: "#home" },
  { name: "Men haqimda", href: "#about" },
  { name: "Ko'nikmalar", href: "#skills" },
  { name: "Loyihalar", href: "#projects" },
  { name: "Tajriba", href: "#experience" },
  { name: "Bog'lanish", href: "#contact" }
]

function scrollToSection(href) {
  const element = document.querySelector(href)
  if (element) {
    element.scrollIntoView({ behavior: "smooth" })
  }
  isMenuOpen.value = false
}
</script>

<template>
  <header class="header">
    <nav class="nav">
      <div class="logo">Portfolio</div>

      <!-- Desktop Navigation -->
      <div class="nav-links">
        <button
          v-for="item in navItems"
          :key="item.name"
          @click="scrollToSection(item.href)"
          class="nav-link"
        >
          {{ item.name }}
        </button>
      </div>

      <!-- Mobile Menu Button -->
      <button class="menu-btn" @click="isMenuOpen = !isMenuOpen">
        <span v-if="!isMenuOpen">☰</span>
        <span v-else>✖</span>
      </button>
    </nav>

    <!-- Mobile Navigation -->
    <div v-if="isMenuOpen" class="mobile-menu">
      <button
        v-for="item in navItems"
        :key="item.name"
        @click="scrollToSection(item.href)"
        class="mobile-link"
      >
        {{ item.name }}
      </button>
    </div>
  </header>
</template>

<style scoped>
.header {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  background: rgba(255, 255, 255, 0.9);
  backdrop-filter: blur(6px);
  border-bottom: 1px solid #e5e7eb;
  z-index: 50;
}
.nav {
  max-width: 1300px;
  margin: auto;
  padding: 16px 20px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.logo {
  font-weight: 600;
}
.nav-links {
  display: none;
}
.nav-link {
  margin-left: 24px;
  color: #6b7280;
  background: none;
  border: none;
  cursor: pointer;
  font-size: 15px;
  font-weight: 500;
  transition: color 0.2s;
}
.nav-link:hover {
  color: #111827;
}
.menu-btn {
  background: none;
  border: none;
  font-size: 20px;
  cursor: pointer;
}
.mobile-menu {
  background: white;
  border-bottom: 1px solid #e5e7eb;
  padding: 16px;
  display: flex;
  flex-direction: column;
  gap: 12px;
}
.mobile-link {
  text-align: left;
  background: none;
  border: none;
  color: #6b7280;
  font-size: 16px;
  cursor: pointer;
  transition: color 0.2s;
}
.mobile-link:hover {
  color: #111827;
}

/* Responsive */
@media (min-width: 768px) {
  .nav-links {
    display: flex;
    align-items: center;
  }
  .menu-btn,
  .mobile-menu {
    display: none;
  }
}
</style>
