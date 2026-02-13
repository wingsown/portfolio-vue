<template>
  <section class="home section" id="home">
    <div class="home__container container grid">
      <div class="home__content grid">

        <div class="home__social">
          <a href="https://www.linkedin.com/in/wilsonbuena" target="_blank" class="home__social-icon">
            <i class="uil uil-linkedin-alt"></i>
          </a>

          <a href="https://www.github.com/wingsown" target="_blank" class="home__social-icon">
            <i class="uil uil-github-alt"></i>
          </a>

          <a href="https://wilson-journal.netlify.app" target="_blank" class="home__social-icon">
            <i class="bx bx-book"></i>
          </a>
        </div>

        <div class="home__img">
          <img src="@/assets/img/wilson_3.png" alt="Wilson" class="about__img" />
        </div>

        <div class="home__data">
          <h1 class="home__title">Hi, I'm Wilson</h1>
          <h3 class="home__subtitle">Software Engineer</h3>

          <p class="home__description">
            I enhance user-facing apps with better UI/UX and performance,
            build clean scalable code, and set best practices
            for frontend development.
          </p>

          <a href="#contact" class="button button--flex">
            Contact Me <i class="uil uil-envelope button__icon"></i>
          </a>
        </div>

      </div>

      <div class="home__scroll">
        <a href="#portfolio" class="home__scroll-button button--flex">
          <i class="uil uil-mouse-alt home__scroll-mouse"></i>
        </a>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
// No logic needed yet
</script>
