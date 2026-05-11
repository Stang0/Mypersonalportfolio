<script setup>
import heroImage from '../assets/hero.png'
</script>

<template>
  <section id="home" class="hero-grid relative isolate min-h-screen scroll-mt-24 overflow-hidden px-6 py-28">
    <div class="relative z-10 mx-auto grid h-screen w-full max-w-7xl items-center gap-12 lg:grid-cols-2 lg:px-4">
      <div class="relative mx-auto w-full max-w-sm lg:mx-0 lg:justify-self-center">
        <div class="relative aspect-square overflow-hidden rounded-full shadow-2xl shadow-primary">
          <img
            :src="heroImage"
            alt="Portfolio hero portrait"
            class="h-full w-full scale-180 object-contain p-10"
          />
        </div>
      </div>

      <div class="max-w-3xl text-center lg:text-left">
        <h1 class="text-5xl font-black leading-tight tracking-normal md:text-6xl lg:text-7xl">
          <span class="text-primary">My Portfolio</span>
          <br/>
          <h3 class="text-4xl font-bold text-text-main">Veerapat Chewprecha</h3>
        </h1>
        <p class="mx-auto mt-8 max-w-xl text-base leading-7 text-text-muted lg:mx-0">
          This is my personal portfolio website, showcasing my frontend development projects,  Explore my journey and skills in web development 
        </p>
        <a
          href="#resume"
          class="mt-7 inline-flex h-12 items-center justify-center rounded-full border border-text-main px-9 text-sm font-bold text-text-main transition hover:border-primary hover:bg-primary hover:text-white"
        >
          My Resume
        </a>
      </div>
    </div>
  </section>
</template>
