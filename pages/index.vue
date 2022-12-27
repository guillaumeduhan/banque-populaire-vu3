<script setup>
import { ref } from "vue";
const accounts = ref([
  {
    icon: "./card.png",
    title: "Compte courant",
    amount: 3202.22,
    last_operation: {
      date: "hier à 12h23",
      amount: 124.33,
      title: "La Coupole, PARIS 14",
    },
  },
  {
    icon: "./wallet.png",
    title: "Livret A",
    amount: 14654.44,
    detail: "Taux journalier: 2.32% — il y a 1 heure",
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
  {
    icon: "./bitcoin.png",
    title: "Compte Bitcoins",
    amount: 12000.0,
    amount_btc: 1.2,
    detail: "1 BTC = 10,000 € — il y a 1 minute",
  },
]);
</script>

<template>
  <div class="flex flex-col w-full p-3 lg:py-6 lg:px-10">
    <Header />
    <main class="grid gap-4 xl:grid-cols-4">
      <div class="xl:col-span-3">
        <div class="grid gap-4 lg:grid-cols-2">
          <Account v-for="(item, index) in accounts" :key="index" :account="item" />
        </div>
        <Payments />
      </div>
      <div class="w-full xl:col-span-1">
        <Concil />
        <History />
      </div>
    </main>
  </div>
</template>

<style lang="scss"></style>
