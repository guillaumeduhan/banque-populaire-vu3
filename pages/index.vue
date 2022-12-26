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
  <div class="flex flex-col w-full px-10 py-6">
    <Header />
    <main class="grid grid-cols-4 gap-4">
      <div class="col-span-3">
        <div class="grid grid-cols-2 gap-4">
          <Account
            v-for="(item, index) in accounts"
            :key="index"
            :account="item"
          />
        </div>
        <Payments />
      </div>
      <div class="col-span-1">
        <History />
      </div>
    </main>
  </div>
</template>

<style lang='scss'></style>