<script setup>
import { ref } from 'vue'

const isOpen = ref(false)

const toggleMenu = () => {
  isOpen.value = !isOpen.value
}
</script>
<template>
  <header class="bg-[#FDFBFA] shadow-md sticky top-0 z-50">
    <nav class="container mx-auto px-6 py-4 flex justify-between items-center">
      <div class="text-2xl font-bold text-[#322D29] tracking-wide">Iqbal</div>

      <button
        class="md:hidden text-[#322D29] focus:outline-none"
        @click="toggleMenu"
        aria-label="Toggle menu"
      >
        <svg
          v-if="!isOpen"
          xmlns="http://www.w3.org/2000/svg"
          class="h-6 w-6"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M4 6h16M4 12h16M4 18h16"
          />
        </svg>
        <svg
          v-else
          xmlns="http://www.w3.org/2000/svg"
          class="h-6 w-6"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M6 18L18 6M6 6l12 12"
          />
        </svg>
      </button>

      <!-- Desktop Menu -->
      <ul class="hidden md:flex space-x-6 text-sm font-medium text-[#322D29]">
        <li><a href="#profil" class="hover:text-[#72383D] transition">Profil</a></li>
        <li><a href="#pendidikan" class="hover:text-[#72383D] transition">Pendidikan</a></li>
        <li><a href="#skill" class="hover:text-[#72383D] transition">Skill</a></li>
        <li><a href="#proyek" class="hover:text-[#72383D] transition">Proyek</a></li>
        <li><a href="#kontak" class="hover:text-[#72383D] transition">Kontak</a></li>
      </ul>
    </nav>

    <!-- Mobile Menu with transition -->
    <transition name="slide-fade">
      <div v-if="isOpen" class="md:hidden px-6 pb-4 bg-[#FDFBFA]">
        <ul class="flex flex-col space-y-3 text-sm font-medium text-[#322D29]">
          <li><a href="#profil" @click="toggleMenu" class="hover:text-[#72383D]">Profil</a></li>
          <li><a href="#pendidikan" @click="toggleMenu" class="hover:text-[#72383D]">Pendidikan</a></li>
          <li><a href="#skill" @click="toggleMenu" class="hover:text-[#72383D]">Skill</a></li>
          <li><a href="#proyek" @click="toggleMenu" class="hover:text-[#72383D]">Proyek</a></li>
          <li><a href="#kontak" @click="toggleMenu" class="hover:text-[#72383D]">Kontak</a></li>
        </ul>
      </div>
    </transition>
  </header>
</template>

<style scoped>
.slide-fade-enter-active {
  transition: all 0.3s ease;
}
.slide-fade-leave-active {
  transition: all 0.2s ease;
}
.slide-fade-enter-from {
  opacity: 0;
  transform: translateY(-10px);
}
.slide-fade-leave-to {
  opacity: 0;
  transform: translateY(-10px);
}
</style>
