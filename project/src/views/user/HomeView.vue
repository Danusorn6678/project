<script setup> 
import UserLayout from '@/layouts/UserLayout.vue'
import videoSrc from '@/assets/hiv.mp4'
</script>

<template>
  <UserLayout>
    <!-- Hero Section with Video -->
    <div class="hero h-96 relative">
      <video autoplay muted loop class="absolute inset-0 w-full h-full object-cover">
        <source :src="videoSrc" type="video/mp4">
        Your browser does not support the video tag.
      </video>

      <div class="hero-overlay bg-black bg-opacity-50 absolute inset-0"></div>

      <div class="hero-content text-neutral-content text-center relative z-10">
        <div class="max-w-lg mx-auto p-8 bg-gradient-to-br from-black via-gray-900 to-transparent rounded-lg shadow-2xl">
          <h1 class="mb-6 text-6xl font-extrabold text-transparent bg-clip-text bg-gradient-to-r from-yellow-400 via-red-500 to-pink-600 drop-shadow-2xl">
            Basic First Aid
          </h1>
          <p class="mb-6 text-xl font-semibold text-gray-200">
            Master essential skills to save lives and handle emergencies with confidence.
          </p>
          <button class="btn btn-primary text-lg px-6 py-3 rounded-full shadow-lg transform transition-transform hover:scale-105">
            Get Started
          </button>
        </div>
      </div>
    </div>

    <!-- Cards Section -->
    <section class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4 p-4">
      <!-- Card Template -->
      <div class="max-w-[16rem] rounded-lg shadow bg-[#ffff]">
        <img class="rounded-t-lg w-full" src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRoZipjHNQxuMm6G_nQECFnkod-GHaMQR8omA&s" alt="Card Image" />
        <div class="p-4">
          <h5 class="mb-2 text-xl font-bold tracking-tight text-[#000] truncate">Noteworthy</h5>
          <p class="mb-3 font-normal text-gray-700 truncate">Here are the biggest enterprise technology acquisitions of 2021 so far.</p>
          <div class="flex justify-end items-center pt-3">
            <a href="#" class="text-[white] bg-[#ff5722] focus:outline-none focus:ring-4 font-medium rounded-full text-sm px-12 py-2 text-center inline-block">
              Buy now
            </a>
          </div>
        </div>
      </div>

      <!-- Repeat the card template as needed -->
    </section>
  </UserLayout>
</template>

<style scoped>
.hero-content h1 {
  background: linear-gradient(90deg, rgba(255,223,0,1) 0%, rgba(255,0,0,1) 50%, rgba(255,105,180,1) 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  text-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
}
</style>
