<script setup lang="ts"></script>

<template>
  <div id="hero" class="hero min-h-screen">
    <!-- <div class="hero-overlay">
      <canvas ref="canvas"> </canvas>
    </div> -->
    <div class="hero-content text-neutral-content text-center">
      <div class="max-w-2xl">
        <h1 class="mb-5 text-7xl font-bold" ref="main">Hey there, I'm <span class="text-green-500">Leo</span>.</h1>
        <p class="mb-5 text-2xl" ref="second">Welcome to my Site.</p>
        <button
          class="btn btn-primary rounded-xl border-2 border-solid hover:border-[var(--color-green-500)]"
        >
          <a href="#about">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              height="24px"
              viewBox="0 -960 960 960"
              width="24px"
              class="fill-current"
            >
              <path d="M480-344 240-584l56-56 184 184 184-184 56 56-240 240Z" />
            </svg>
          </a>
        </button>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
