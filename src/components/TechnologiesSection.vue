<script setup lang="ts">
import { ref } from 'vue'
import { getImageUrl } from '@/composables/utils'

interface Item {
  name: string
  proficiency: string
  description: string
}

const selectedAccordion = ref('0')

const tech: Record<string, Item[]> = {
  Languages: [
    {
      name: 'English',
      proficiency: "IT'S OVER 9000!",
      description:
        'A language I can confidently say I have 20+ years of professional experience in reading and writing. Proficient in communication skills, specialisation in the Australian dialect.',
    },
    {
      name: 'Chinese',
      proficiency: "IT'S OVER 9000!",
      description:
        'The only other language I can confidently say I have 20+ years of professional experience in, though growing up in a predominantly English-speaking society has left my blades a bit rusted.',
    },
    {
      name: 'Python',
      proficiency: "IT'S ALMOST OVER 9000!",
      description:
        'If I had to choose one programming language to use for the rest of my life, Python would be it.',
    },
    {
      name: 'C',
      proficiency: 'Can teach it, might cry afterward.',
      description:
        'The holy grail of programming languages. Long live C. Screw segmentation faults though.',
    },
    {
      name: 'Java',
      proficiency: "Battle-tested. Just don't ask me to love it.",
      description:
        'Verbose? Yes. Reliable? Also yes. public static void main still lives rent-free in my head.',
    },
    {
      name: 'JavaScript',
      proficiency: 'Fluent in chaos.',
      description:
        'Where "b" + "a" + + "a" + "a" gives you "banana" — and I somehow still trust it to run my frontend.',
    },
    {
      name: 'CSharp',
      proficiency: 'If I know Java, I know C#... right?',
      description:
        'The language itself is nice, but to get Unity to cooperate is a whole other story...',
    },
    {
      name: 'R',
      proficiency: 'I fear I may never become semi-proficient.',
      description:
        'I thought Python would be better for stats. Then I looked at the Pandas documentation.',
    },
  ],
  Frameworks: [
    {
      name: 'Vue',
      proficiency: 'I will master it out of obligation.',
      description:
        'I may not be the best at it, but as long as I have my unwavering bias towards Vue, eventually I will become the best.',
    },
    {
      name: 'Express',
      proficiency: '8/10.',
      description:
        "I would've made a proficiency joke, but express.js is just respectable. It's minimal and gets the job done.",
    },
    {
      name: 'Tailwind',
      proficiency: 'Capable with documentation.',
      description:
        'Because of CSS, I started using Tailwind, but because of Tailwind, I had to keep on learning CSS.',
    },
  ],
  Other: [
    {
      name: 'Git',
      proficiency: 'Can use it, but may never truly master it.',
      description: 'git push --force, and watch the fires burn.',
    },
    {
      name: 'CSS',
      proficiency: 'Debugging nightmare.',
      description: 'The root cause of 90% of my bottlenecks during coding :/.',
    },
    {
      name: 'HTML',
      proficiency: '9/10.',
      description:
        'Occasional hiccups from forgetting element attributes, but never had the same head bashing experience as CSS.',
    },
    {
      name: 'SQL',
      proficiency: 'Decent.',
      description: 'Understanding a database model is harder than creating the actual queries.',
    },
    {
      name: 'Typescript',
      proficiency: 'Stack Overflow eternally open.',
      description: 'Can work, but when the errors start coming it, it is nigh undebuggable.',
    },
  ],
  Learning: [
    {
      name: 'Docker',
      proficiency: "'now what it does, haven't broken anything with it. Yet.",
      description:
        "Have read enough Dockerfiles to pretend I know what I'm doing. Will make it real soon.",
    },
  ],
}
</script>

<template>
  <div id="skills" class="divider divider-accent"></div>
  <div class="w-9/10 mx-auto mb-12 mt-24">
    <h2 class="mb-4 text-5xl tracking-tight font-bold">Technical Showcase</h2>
    <p class="mb-5 text-2xl">
      Over the years, I've found myself dabbling in various programming languages, frameworks, and
      technologies. Below is a showcase of them:
    </p>

    <div
      class="collapse collapse-arrow bg-base-100 border border-base-300"
      v-for="(value, key, index) in tech"
      :key="index"
    >
      <input
        type="radio"
        name="my-accordion-2"
        :checked="selectedAccordion === `${index}`"
        @change="selectedAccordion = `${index}`"
      />
      <div class="collapse-title font-semibold">{{ key }}</div>
      <div class="collapse-content text-sm">
        <ul class="list bg-base-100 rounded-box shadow-md">
          <li class="list-row" v-for="(item, idx) in value" :key="idx">
            <div>
              <img class="size-10 object-contain rounded-box" :src="getImageUrl(item.name)" />
            </div>
            <div>
              <div>{{ item.name }}</div>
              <div class="text-xs font-semibold opacity-60">
                Proficiency: {{ item.proficiency }}
              </div>
            </div>
            <p class="list-col-wrap text-xs">
              {{ item.description }}
            </p>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
