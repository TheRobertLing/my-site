<script setup lang="ts">
import { ref } from 'vue'
import { useToast } from 'vue-toastification'
const WEB3FORMS_ACCESS_KEY = 'f786d4e2-21fb-4ad2-b625-eefba9666c66' // Le trolled not api key i can store it here hehe
const name = ref('')
const email = ref('')
const message = ref('')
const toast = useToast()

const submitForm = async () => {
  const response = await fetch('https://api.web3forms.com/submit', {
    method: 'POST',
    headers: {
      'Content-Type': 'application/json',
      Accept: 'application/json',
    },
    body: JSON.stringify({
      access_key: WEB3FORMS_ACCESS_KEY,
      name: name.value,
      email: email.value,
      message: message.value,
    }),
  })
  const result = await response.json()
  if (result.success) {
    toast.success('Message successfully sent', {
      timeout: 5000,
    })
    name.value = ''
    email.value = ''
    message.value = ''
  }
}
</script>

<template>
  <div id="contact" class="divider divider-accent"></div>
  <div class="w-9/10 mx-auto mt-24">
    <div class="py-8 lg:py-16 px-4 mx-auto max-w-screen-md">
      <h2 class="mb-4 text-5xl tracking-tight font-bold text-center">Get in Contact</h2>
      <p class="mb-8 lg:mb-16 text-center sm:text-xl">
        I will eagerly await for any messages to come through :D
      </p>

      <form @submit.prevent="submitForm" class="space-y-8">
        <div>
          <label for="name" class="block mb-2 text-sm font-medium">Name</label>
          <input
            id="name"
            class="border border-gray-300 text-sm rounded-lg focus:ring-primary-500 focus:border-primary-500 block w-full p-2.5"
            type="text"
            name="name"
            placeholder="John Doe"
            v-model="name"
            required
          />
        </div>

        <div>
          <label for="email" class="block mb-2 text-sm font-medium">Your email</label>
          <input
            type="email"
            id="email"
            name="email"
            class="border border-gray-300 text-sm rounded-lg focus:ring-primary-500 focus:border-primary-500 block w-full p-2.5"
            placeholder="exampleemail@gmail.com"
            v-model="email"
            required
          />
        </div>

        <div>
          <label for="message" class="block mb-2 text-sm font-medium">Your message</label>
          <textarea
            id="message"
            rows="6"
            class="border border-gray-300 text-sm rounded-lg focus:ring-primary-500 focus:border-primary-500 block w-full p-2.5"
            placeholder="Leave a comment..."
            v-model="message"
          ></textarea>
        </div>

        <button class="btn btn-block" type="submit">Submit Form</button>
      </form>
    </div>
  </div>
</template>

<style scoped></style>
