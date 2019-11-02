<template>
  <div class="flex flex-col min-h-screen app-wrap">
    <main class="flex-1">
      <div class="py-20 hero bg-green-600">
        <div class="hero-container mx-auto px-6">
          <h1 class="text-4xl font-bold mb-2">
            {{ message }}
          </h1>
          <p class="text-2xl">
            Your IP: {{ ip }}
          </p>
        </div>
      </div>
      <section class="container mx-auto px-6 p-10">
        <h2 class="text-4xl font-bold text-center text-gray-800 mb-8">
          Features
        </h2>
        <div class="flex items-center flex-wrap mb-20">
          <div class="w-full md:w-1/2 flex flex-col justify-between px-4">
            <a href="https://tailwindcss.com/" target="_blank" class="mb-8 rounded-lg px-4 md:px-5 xl:px-4 py-3 md:py-4 xl:py-3 bg-white hover:bg-gray-200 md:text-lg xl:text-base text-gray-800 font-semibold leading-tight shadow-md">
              TailwindCSS
            </a>
            <a href="https://nuxtjs.org/" target="_blank" class="mb-8 rounded-lg px-4 md:px-5 xl:px-4 py-3 md:py-4 xl:py-3 bg-white hover:bg-gray-200 md:text-lg xl:text-base text-gray-800 font-semibold leading-tight shadow-md">
              NuxtJS
            </a>
            <p class="text-gray-600 px-6">Create classes in assets/styles and apply Tailwind classes using @apply</p>
          </div>
          <div class="w-full md:w-1/2">
            <img src="https://www.dropbox.com/s/mimcvn6zxtoruis/health.svg?raw=1" alt="Monitoring"/>
          </div>
        </div>
      </section>
    </main>
  </div>
</template>

<script>
export default {
  name: 'Index',
  data() {
    return {
      message: 'Tailwind NuxtJS Starter',
      ip: ''
    }
  },
  async asyncData(context) {
    const res = await context.$http.$get('https://api.ipify.org?format=json')
    return { ip: res.ip }
  }
}
</script>

<style scoped>

</style>
