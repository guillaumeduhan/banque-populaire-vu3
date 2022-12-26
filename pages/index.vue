<script setup>
import { ref } from "vue";
const accounts = ref([
  {
    icon: "./card.png",
    title: "Compte courant",
    amount: 3202.22,
    last_operation: {
      date: "Hier à 12h23",
      amount: 124.33,
      title: "Restaurant La Coupole, PARIS 14",
    },
  },
  {
    icon: "./wallet.png",
    title: "Livret A",
    amount: 14654.44,
    detail: "Taux journalier: 2.32% — mis à jour il y a 1 heure",
  },
  {
    icon: "./cheque.png",
    title: "Compte chèques",
    amount: -90.0,
    last_operation: {
      date: "Samedi à 19h55",
      amount: 15.5,
      title: "UBEREATS",
    },
  },
]);
</script>

<template>
  <div class="flex flex-col w-full px-10 py-6">
    <Header />
    <div class="flex items-center justify-between mb-6">
      <div class="flex items-center justify-start notification">
        <IconsMessage class="mr-1 text-xl" />
        <span class="mr-1">
          1 message non-lu de la part de votre conseiller.
        </span>
        <span class="underline cursor-pointer">Cliquez ici pour le lire.</span>
      </div>
      <div class="text-sm description">
        Dernière connexion: hier à 12h22 depuis iPhone 12.
      </div>
    </div>
    <main class="grid grid-cols-4 gap-4">
      <div class="grid grid-cols-2 col-span-3 gap-4">
        <Account
          v-for="(item, index) in accounts"
          :key="index"
          :account="item"
        />
      </div>
      <div class="col-span-1">
        <h2>Historique des opérations</h2>
      </div>
    </main>
  </div>
</template>

<style lang='scss'></style>