<script setup lang="ts"></script>

<template>
  <div class="hero min-h-screen">
    <div class="hero-overlay">
      <canvas ref="canvas">
        

      </canvas>
    </div>
    <div class="hero-content text-neutral-content text-center">
      <div class="max-w-md">
        <h1 class="mb-5 text-5xl font-bold">Hey there, I'm Leo</h1>
        <p class="mb-5">Welcome to my site.</p>
        <button class="btn btn-primary rounded-xl border-2 border-solid hover:border-[var(--color-neutral-content)]">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            height="24px"
            viewBox="0 -960 960 960"
            width="24px"
            class="fill-current"
          >
            <path d="M480-344 240-584l56-56 184 184 184-184 56 56-240 240Z" />
          </svg>
        </button>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
