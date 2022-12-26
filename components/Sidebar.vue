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
  <div class="flex flex-col h-screen Sidebar">
    <header class="p-6">
      <img class="w-48" src="/logo.png" alt="Banque Populaire" />
    </header>
    <main class="grow">
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
    <footer class="p-6">
      <p class="p-3 text-xs rounded-lg description bg-slate-100">
        Cyberplus v4 — produit bancaire revisité par Guillaume Duhan à
        l'occasion du Think tank de Mai 2022.
      </p>
    </footer>
  </div>
</template>

<style lang='scss'></style>