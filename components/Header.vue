<script setup></script>

<template>
  <div class="flex items-center justify-between mt-2 mb-8 Header">
    <div>
      <h1>Bienvenue Mr Guillaume Duhan</h1>
      <p class="description">
        Votre espace Cyberplus vous permet d'effectuer toutes les opérations courantes.
      </p>
    </div>
    <div class="flex items-center justify-start">
      <div
        class="hidden lg:flex grid grid-cols-2 gap-3 mr-2 text-2xl text-gray-400 cursor-pointer"
      >
        <div class="relative">
          <IconsMessage class="text-blue-600" />
          <div
            class="absolute w-4 h-4 text-xs font-bold text-center text-white bg-red-500 rounded-full -right-2 -top-2"
          >
            1
          </div>
        </div>
        <IconsBell class="hover:text-blue-600" />
      </div>
      <div class="relative">
        <div
          class="absolute lg:hidden w-4 h-4 text-xs font-bold text-center text-white bg-red-500 rounded-full -right-0 -top-0"
        >
          1
        </div>
        <div class="avatar">
          <img src="/me.png" alt="Guillaume Duhan" />
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss"></style>
