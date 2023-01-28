<script lang="ts" setup>
  useHead({
    title: 'Home',
    meta: [
      { 
        name: 'description', 
        content: 'Home Nuxt 3, IT Trat Department' 
      },
      {
        name: 'keywords',
        content: 'Home, Nuxt 3, Learning Nuxt 3'
      },
    ],
  })
</script>

<template>
  <div>
    
    <section
      id="hero"
      class="grid -mt-1 bg-skin-fill sm:h-screen place-items-center sm:mt-0 hero-default"
    >
      <div
        class="container flex flex-col items-center justify-between gap-6 px-4 mx-auto xl:px-0 sm:flex-row sm:gap-20"
      >
        <div class="w-full sm:w-6/12">
          <h1 class="text-4xl sm:text-6xl font-bold xl:leading-[4rem] text-skin-base">
            Nuxt 3 Tailwind
          </h1>
          <p class="mt-4 text-xl mb-14 text-skin-muted">
            Nuxt 3 + Tailwind CSS for Starter kit
          </p>
          <div class="space-x-4">
            <button class="px-4 py-3 text-2xl text-white bg-teal-700 rounded-lg">
              Get Starte
            </button>
          </div>
        </div>
        <div class="flex justify-end w-full p-6 sm:w-6/12 sm:p-0">
          <img loading="lazy" src="~/assets/images/speaker.jpg" alt="" class="w-auto rounded-lg animate-pulse">
        </div>
      </div>
    </section>

  </div>
</template>