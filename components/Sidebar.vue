<script setup>
const menu = [
  "Mon espace",
  "Mes comptes",
  "Mes opérations",
  "Gérer au quotidien",
  "Epargner",
  "Emprunter/assurer",
];

const underMenu = [
  "Votre banque",
  "Service informatique",
  "Information pratique",
  "Tarifs et réglementations",
  "Banque en ligne",
  "Se déconnecter",
];
</script>

<template>
  <div
    class="flex py-2 lg:py-2 lg:flex-col items-center lg:items-start lg:h-screen Sidebar"
  >
    <header class="w-auto lg:w-full mb-4">
      <img class="w-32 lg:w-48" src="/logo.png" alt="Banque Populaire" />
    </header>
    <main class="hidden lg:block grow">
      <ul class="menu">
        <li v-for="(item, index) in menu" :key="index">
          <span>{{ item }}</span>
          <IconsRight class="icon" />
        </li>
      </ul>
      <ul class="underMenu">
        <li v-for="(item, index) in underMenu" :key="index">{{ item }}</li>
      </ul>
    </main>
    <footer class="m-4">
      <div class="flex rounded-lg text-green-500 bg-green-100 px-2 py-2 mx-2 w-full">
        <div class="mr-2">
          <IconsInfo class="text-lg text-green-500" />
        </div>
        <span class="text-xs"
          >Cyberplus v4 revisité par Guillaume Duhan pour le think tank de Mai 2022.</span
        >
      </div>
    </footer>
  </div>
</template>

<style lang="scss"></style>
