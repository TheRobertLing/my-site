<script setup lang="ts"></script>

<template>
  <div id="about" class="divider divider-accent"></div>
  <div class="w-9/10 mx-auto flex flex-col lg:flex-row justify-center items-center mt-24">
    <div class="p-6 lg:w-4/10 flex justify-center items-center max-w-screen-md grow">
      <figure class="flex flex-col items-center">
        <img
          class="w-xs h-xs rounded-full border-2 border-solid transition hover:border-[var(--color-green-500)]"
          src="../assets/husk.png"
          alt="Profile"
        />

        <figcaption class="text-center p-6 w-8/10">
          "Actuarial Studies teaches me to manage risk. Computer Science ensures I create it.
          Perfectly balanced, like all things should be."
        </figcaption>
      </figure>
    </div>
    <div class="p-6 lg:w-6/10 flex flex-col justify-center grow">
      <h2 class="mb-5 text-5xl font-bold">An Obligatory Self Introduction?🤔</h2>
      <p class="mb-5 text-2xl">
        Hi, I'm Leo, and I'm currently a third year university student studying a double degree in
        Actuarial Studies and Computer Science. But perhaps a more apt description would be an
        newbie statistician who has stumbled into the rabbithole that is JavaScript and software
        engineering 😶.
      </p>
      <p class="mb-5 text-2xl">
        I aspire to one day combine my experience in data processing and implementing modern machine
        learning and algorithmic technologies to build software that enhances natural language
        processing and makes communication across languages more seamless and accessible.
      </p>
      <p class="mb-5 text-2xl">
        In my spare time, I enjoy playing old-school arcade style games. The
        <a
          class="hover:cursor-pointer transition hover:text-green-500"
          href="https://en.wikipedia.org/wiki/Doom_(franchise)"
          target="_blank"
          >DOOM</a
        >
        series is among my favourites.
        <a
          class="hover:cursor-pointer transition hover:text-green-500"
          href="https://www.teamfortress.com/"
          target="_blank"
          >TF2</a
        >
        is another one of my all time favourite video games. I have recently also starting picking
        up the electric guitar.
      </p>
    </div>
  </div>
</template>

<style scoped></style>
