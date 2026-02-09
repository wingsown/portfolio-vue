<template>
  <header class="header" id="header">
    <nav class="nav container">
      <!-- Logo -->
      <a href="#" class="nav__logo">
        <!-- <img
          src="@/assets/img/Icon_4.png"
          alt="Logo"
          class="nav__logo-img logo-img"
        /> -->
      </a>

      <!-- Menu -->
      <div class="nav__menu" :class="{ 'show-menu': isMenuOpen }">
        <ul class="nav__list grid">
          <li
            v-for="item in navItems"
            :key="item.id"
            class="nav__item"
          >
            <a
              :href="item.href"
              class="nav__link"
              :class="{ 'active-link': activeSection === item.id }"
              @click="closeMenu"
            >
              <i :class="item.icon" class="nav__icon"></i>
              {{ item.label }}
            </a>
          </li>
        </ul>

        <!-- Close button -->
        <i
          class="uil uil-times nav__close"
          @click="closeMenu"
        ></i>
      </div>

      <!-- Buttons -->
      <div class="nav__btns">
        <!-- Theme toggle -->
        <i
          class="uil change-theme"
          :class="isDark ? 'uil-sun' : 'uil-moon-eclipse'"
          @click="toggleTheme"
        ></i>

        <!-- Mobile toggle -->
        <div class="nav__toggle" @click="openMenu">
          <i class="uil uil-apps"></i>
        </div>
      </div>
    </nav>
  </header>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const isMenuOpen = ref(false)
const isDark = ref(false)
const activeSection = ref('home')

const navItems = [
  { id: 'home', href: '#home', label: 'Home', icon: 'uil uil-estate' },
  { id: 'portfolio', href: '#portfolio', label: 'Portfolio', icon: 'uil uil-folder' },
  { id: 'skills', href: '#skills', label: 'Skills', icon: 'uil uil-file-alt' },
  { id: 'qualification', href: '#qualification', label: 'Qualifications', icon: 'uil uil-graduation-cap' },
  { id: 'services', href: '#services', label: 'Services', icon: 'uil uil-briefcase-alt' },
  { id: 'about', href: '#about', label: 'Profile', icon: 'uil uil-user' },
  { id: 'contact', href: '#contact', label: 'Contact', icon: 'uil uil-message' }
]

const openMenu = () => {
  isMenuOpen.value = true
}

const closeMenu = () => {
  isMenuOpen.value = false
}

const toggleTheme = () => {
  isDark.value = !isDark.value
  document.body.classList.toggle('dark-theme', isDark.value)
  localStorage.setItem('theme', isDark.value ? 'dark' : 'light')
}

onMounted(() => {
  const savedTheme = localStorage.getItem('theme')
  if (savedTheme === 'dark') {
    isDark.value = true
    document.body.classList.add('dark-theme')
  }
})
</script>
