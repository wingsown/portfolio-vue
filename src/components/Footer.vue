<template>
  <footer class="footer">
    <div class="footer__bg">
      <div class="footer__container container grid">
        
        <!-- LINKS -->
        <div>
          <ul class="footer__links">
            <li v-for="link in footerLinks" :key="link.href">
              <a :href="link.href" class="footer__link">
                {{ link.label }}
              </a>
            </li>
          </ul>
        </div>

        <!-- SOCIALS -->
        <div class="footer__socials">
          <a
            v-for="social in socials"
            :key="social.href"
            :href="social.href"
            target="_blank"
            rel="noopener"
            class="footer__social"
          >
            <i :class="social.icon"></i>
          </a>
        </div>
      </div>

      <!-- COPYRIGHT -->
      <p class="footer__copy">
        Coded with ❤️ by Wilson © {{ year }}
      </p>
    </div>
  </footer>
</template>

<script setup lang="ts">
const year = new Date().getFullYear()

const footerLinks = [
  { href: '#portfolio', label: 'Portfolio' },
  { href: '#services', label: 'Services' },
  { href: '#about', label: 'Profile' }
]

const socials = [
  {
    href: 'https://www.linkedin.com/in/wilsonbuena',
    icon: 'uil uil-linkedin'
  },
  {
    href: 'https://www.github.com/wingsown',
    icon: 'uil uil-github'
  },
  {
    href: 'https://wilson-journal.netlify.app',
    icon: 'bx bx-book'
  }
]
</script>
