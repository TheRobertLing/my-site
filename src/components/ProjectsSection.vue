<script setup lang="ts">
import { getImageUrl } from '@/composables/utils'

interface Project {
  name: string
  status: string
  description: string
  stack: string[]
  link: string
  demonstration?: string
}

const projects: Project[] = [
  {
    name: 'flowZH',
    status: 'Live MVP',
    description:
      'A web platform for learning Chinese through interactive games and downloadable resources, designed with a focus on accessibility and community contributions.',
    stack: ['Vue.js', 'TypeScript', 'Express.js', 'Supabase'],
    link: 'https://github.com/TheRobertLing/flowZH',
  },
  {
    name: 'ZiTube',
    status: 'In Development',
    description:
      'A video platform for Chinese learners that integrates subtitles, inline translations, and full transcripts to support immersive language learning.',
    stack: ['Vue.js', 'TypeScript', 'Laravel'],
    link: 'https://github.com/TheRobertLing/zitube-frontend',
  },
  {
    name: 'zdic-parser',
    status: 'Complete, Actively Maintained',
    description:
      'A tool I created in Python to scrape and parse Chinese character data from ZDic for future projects.',
    stack: ['Python', 'BeautifulSoup', 'PyTest'],
    link: 'https://github.com/TheRobertLing/zdic-parser',
  },
  {
    name: 'pinyin-tools',
    status: 'Complete, Actively Maintained',
    description:
      'A utility library I created for working with pinyin that includes functionality such as converting tones to diacritic marks and verifying pinyin.',
    stack: ['Typescript', 'Vitest'],
    link: 'https://github.com/TheRobertLing/pinyin-tools',
  },
  {
    name: 'extract-zhongwen',
    status: 'Complete',
    description:
      'A utility I created to extract chinese characters from a string, inspired by extract-alphanumeric and making use of Unicode Ranges.',
    stack: ['Typescript', 'Jest'],
    link: 'https://github.com/TheRobertLing/extract-zhongwen',
  },
  {
    name: 'chinese-text-segmentation',
    status: 'Work In Progress',
    description:
      'A work in process NLP library designed to segment Chinese text into meaningful words and phrases.',
    stack: ['Python'],
    link: 'https://github.com/TheRobertLing/chinese-text-segmentation',
  },
]
</script>

<template>
  <div id="projects" class="divider divider-accent"></div>
  <div class="w-9/10 mx-auto mt-24">
    <div class="flex justify-center">
      <div class="p-6 lg:w-7/10 flex flex-col justify-start grow">
        <h2 class="mb-5 text-5xl tracking-tight font-bold">My Project Progression</h2>
        <p class="mb-5 text-2xl">
          I feel that the general sentiment nowadays towards personal projects is that you have to
          build them just for the sake of it. Go and build the next Twitter (or X) social media
          platform. Perhaps create a fully functioning e-commerce website equipped with government
          level authentication, an enterprise level database and CDN's for speed. Maybe even
          synthesize J.A.R.V.I.S so you can be dubbed Tony Stark, and push humanity one step closer
          to Judgement Day.
        </p>
        <p class="mb-5 text-2xl">
          All jokes aside, while I by no means wish to imply that I'm a sour grape because I've yet
          to attain such levels of mastery, I feel that there isn't enough time spent appreciating
          how the various components being used is able to slowly come together to form the digital
          software that we can make use of, and the mindset has instead shifted to "Am I using auth?
          Should I use Laravel or Next.js? Am I using a database? Are my backend API's GraphQL
          rather than REST for flexibility? How fast can I push this code into production?".
        </p>
        <p class="mb-5 text-2xl">
          When it comes to personal projects, I've come to believe there's no shame in creating
          something small. A simple Minecraft mod written in Java. A lightweight utility published
          on NPM. Heck, even a single function. Leftpad was only 11 lines of code, yet at one point,
          its impact was arguably greater than React itself, a library that (albeit indirectly)
          depended on it. More importantly, I believe personal projects should first and foremost be
          about experimenting with ideas that interest you. They may not revolutionize the industry,
          but if they serve a purpose for me, I think that is perfectly fine.
        </p>

        <h3 class="mb-4 text-3xl tracking-tight font-bold">Examples of things I've worked on...</h3>

        <div class="flex flex-grow-1 w-full overflow-y-scroll">
          <ul class="list bg-base-100 rounded-box shadow-md w-full">
            <li class="list-row" v-for="(project, index) in projects" :key="index">
              <div>
                <img class="size-10 rounded-box rounded-sm" :src="getImageUrl(project.name)" />
              </div>
              <div>
                <div>{{ project.name }}</div>
                <div class="text-xs font-semibold opacity-60">Status: {{ project.status }}</div>
              </div>
              <div class="list-col-wrap text-xs">
                <p class="mb-2">
                  {{ project.description }}
                </p>

                <div class="flex flex-wrap gap-2">
                  <span
                    class="bg-gray-900 text-xs px-3 py-1 rounded-full"
                    v-for="(stack, idx) in project.stack"
                    :key="idx"
                  >
                    {{ stack }}
                  </span>
                </div>

                <!-- Demonstration Video -->
                <div v-if="project.demonstration">
                  <!-- To-do -->
                </div>
              </div>
              <button class="btn btn-circle hover:border-green-500">
                <a class="w-full h-full" :href="project.link" target="_blank">
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    width="24"
                    height="24"
                    viewBox="0 -3.5 256 256"
                    class="fill-current w-full h-full p-1"
                  >
                    <g>
                      <path
                        d="M127.505 0C57.095 0 0 57.085 0 127.505c0 56.336 36.534 104.13 87.196 120.99 6.372 1.18 8.712-2.766 8.712-6.134 0-3.04-.119-13.085-.173-23.739-35.473 7.713-42.958-15.044-42.958-15.044-5.8-14.738-14.157-18.656-14.157-18.656-11.568-7.914.872-7.752.872-7.752 12.804.9 19.546 13.14 19.546 13.14 11.372 19.493 29.828 13.857 37.104 10.6 1.144-8.242 4.449-13.866 8.095-17.05-28.32-3.225-58.092-14.158-58.092-63.014 0-13.92 4.981-25.295 13.138-34.224-1.324-3.212-5.688-16.18 1.235-33.743 0 0 10.707-3.427 35.073 13.07 10.17-2.826 21.078-4.242 31.914-4.29 10.836.048 21.752 1.464 31.942 4.29 24.337-16.497 35.029-13.07 35.029-13.07 6.94 17.563 2.574 30.531 1.25 33.743 8.175 8.929 13.122 20.303 13.122 34.224 0 48.972-29.828 59.756-58.22 62.912 4.573 3.957 8.648 11.717 8.648 23.612 0 17.06-.148 30.791-.148 34.991 0 3.393 2.295 7.369 8.759 6.117 50.634-16.879 87.122-64.656 87.122-120.973C255.009 57.085 197.922 0 127.505 0"
                      />
                      <path
                        d="M47.755 181.634c-.28.633-1.278.823-2.185.389-.925-.416-1.445-1.28-1.145-1.916.275-.652 1.273-.834 2.196-.396.927.415 1.455 1.287 1.134 1.923M54.027 187.23c-.608.564-1.797.302-2.604-.589-.834-.889-.99-2.077-.373-2.65.627-.563 1.78-.3 2.616.59.834.899.996 2.08.36 2.65M58.33 194.39c-.782.543-2.06.034-2.849-1.1-.781-1.133-.781-2.493.017-3.038.792-.545 2.05-.055 2.85 1.07.78 1.153.78 2.513-.019 3.069M65.606 202.683c-.699.77-2.187.564-3.277-.488-1.114-1.028-1.425-2.487-.724-3.258.707-.772 2.204-.555 3.302.488 1.107 1.026 1.445 2.496.7 3.258M75.01 205.483c-.307.998-1.741 1.452-3.185 1.028-1.442-.437-2.386-1.607-2.095-2.616.3-1.005 1.74-1.478 3.195-1.024 1.44.435 2.386 1.596 2.086 2.612M85.714 206.67c.036 1.052-1.189 1.924-2.705 1.943-1.525.033-2.758-.818-2.774-1.852 0-1.062 1.197-1.926 2.721-1.951 1.516-.03 2.758.815 2.758 1.86M96.228 206.267c.182 1.026-.872 2.08-2.377 2.36-1.48.27-2.85-.363-3.039-1.38-.184-1.052.89-2.105 2.367-2.378 1.508-.262 2.857.355 3.049 1.398"
                      />
                    </g>
                  </svg>
                </a>
              </button>
            </li>
          </ul>
        </div>
      </div>

      <div class="p-6 lg:w-3/10 flex justify-center items-center max-w-screen-md grow">
        <ul class="timeline timeline-snap-icon max-md:timeline-compact timeline-vertical">
          <li>
            <div class="timeline-middle">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 20 20"
                fill="currentColor"
                class="h-5 w-5"
              >
                <path
                  fill-rule="evenodd"
                  d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.857-9.809a.75.75 0 00-1.214-.882l-3.483 4.79-1.88-1.88a.75.75 0 10-1.06 1.061l2.5 2.5a.75.75 0 001.137-.089l4-5.5z"
                  clip-rule="evenodd"
                />
              </svg>
            </div>
            <div class="timeline-start mb-10 md:text-end">
              <time class="font-mono italic">2023</time>
              <div class="text-lg font-black">Tutorial Hell</div>
              Couldn't even finish a single project moving onto another one. Must have like 20
              unfinished projects at this point.
            </div>
            <hr />
          </li>
          <li>
            <hr />
            <div class="timeline-middle">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 20 20"
                fill="currentColor"
                class="h-5 w-5"
              >
                <path
                  fill-rule="evenodd"
                  d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.857-9.809a.75.75 0 00-1.214-.882l-3.483 4.79-1.88-1.88a.75.75 0 10-1.06 1.061l2.5 2.5a.75.75 0 001.137-.089l4-5.5z"
                  clip-rule="evenodd"
                />
              </svg>
            </div>
            <div class="timeline-end md:mb-10">
              <time class="font-mono italic">2023</time>
              <div class="text-lg font-black">The Obligatory React Calculator App</div>
              Because every tutorial told me to build one.
            </div>
            <hr />
          </li>
          <li>
            <div class="timeline-middle">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 20 20"
                fill="currentColor"
                class="h-5 w-5"
              >
                <path
                  fill-rule="evenodd"
                  d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.857-9.809a.75.75 0 00-1.214-.882l-3.483 4.79-1.88-1.88a.75.75 0 10-1.06 1.061l2.5 2.5a.75.75 0 001.137-.089l4-5.5z"
                  clip-rule="evenodd"
                />
              </svg>
            </div>
            <div class="timeline-start mb-10 md:text-end">
              <time class="font-mono italic">2024</time>
              <div class="text-lg font-black">The Leetcode Grind Side Quest</div>
              Ok I'll admit, this one was quite fun, although difficult, as it forced me to think
              critically about how I could translate ideas into code.
            </div>
            <hr />
          </li>
          <li>
            <hr />
            <div class="timeline-middle">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 20 20"
                fill="currentColor"
                class="h-5 w-5"
              >
                <path
                  fill-rule="evenodd"
                  d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.857-9.809a.75.75 0 00-1.214-.882l-3.483 4.79-1.88-1.88a.75.75 0 10-1.06 1.061l2.5 2.5a.75.75 0 001.137-.089l4-5.5z"
                  clip-rule="evenodd"
                />
              </svg>
            </div>
            <div class="timeline-end md:mb-10">
              <time class="font-mono italic">2024</time>
              <div class="text-lg font-black">The Sudoku App</div>
              Experimenting with simple API's for the sake of it. Picked up Vue in favour of React.
            </div>
            <hr />
          </li>

          <li>
            <div class="timeline-middle">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 20 20"
                fill="currentColor"
                class="h-5 w-5"
              >
                <path
                  fill-rule="evenodd"
                  d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.857-9.809a.75.75 0 00-1.214-.882l-3.483 4.79-1.88-1.88a.75.75 0 10-1.06 1.061l2.5 2.5a.75.75 0 001.137-.089l4-5.5z"
                  clip-rule="evenodd"
                />
              </svg>
            </div>
            <div class="timeline-start mb-10 md:text-end">
              <time class="font-mono italic">2024</time>
              <div class="text-lg font-black">Dissatisfaction?</div>
              Building projects had become more of a chore that I despised. "Let us go then, you and
              I, When the evening is spread out against the sky Like a patient etherized upon a
              table;".
            </div>
            <hr />
          </li>

          <li>
            <hr />
            <div class="timeline-middle">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 20 20"
                fill="currentColor"
                class="h-5 w-5"
              >
                <path
                  fill-rule="evenodd"
                  d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.857-9.809a.75.75 0 00-1.214-.882l-3.483 4.79-1.88-1.88a.75.75 0 10-1.06 1.061l2.5 2.5a.75.75 0 001.137-.089l4-5.5z"
                  clip-rule="evenodd"
                />
              </svg>
            </div>
            <div class="timeline-end md:mb-10">
              <time class="font-mono italic">2025</time>
              <div class="text-lg font-black">A Renaissance...</div>
              Ever since shifting my projects to align with my interest for language learning and
              linguistics, I found coding to be exponentially more enjoyable. And they lived happily
              ever after. Or perhaps it's only just the start of a new journey.
            </div>
            <hr />
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
