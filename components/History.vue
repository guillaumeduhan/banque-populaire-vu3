<script setup>
import { ref } from "vue";
const history = ref([
  {
    date: "01/01/23, 16h00",
    title: "Google Salary",
    ref: 323445,
    debit: 0,
    credit: 3432.33,
  },
  {
    date: "29/12/22, 12h22",
    title: "Monoprix",
    ref: 323445,
    debit: 34.55,
    credit: 0,
  },
  {
    date: "29/12/22, 12h00",
    title: "La Poste, Paris 15",
    ref: 323432,
    debit: 12.55,
    credit: 0,
  },
  {
    date: "28/12/22, 19h00",
    title: "Uber Eats",
    ref: 323424,
    debit: 33.55,
    credit: 0,
  },
  {
    date: "26/12/22, 19h00",
    title: "Navigo",
    ref: 323423,
    debit: 84.1,
    credit: 0,
  },
]);
</script>

<template>
  <div class="history">
    <h2 class="mb-4 font-extrabold lg:text-right">
      Historique des opérations (temps réel)
    </h2>
    <div class="grid grid-cols-1 gap-4">
      <div
        class="grid items-center grid-cols-3 history--item"
        v-for="(item, index) in history"
        :key="index"
      >
        <div class="flex truncate" v-if="item.title">{{ item.title }}</div>
        <div class="truncate description" v-if="item.date">{{ item.date }}</div>
        <div class="flex justify-end">
          <div
            class="label"
            :class="item.credit ? 'label--credit' : 'label--debit'"
          >
            {{ item.debit ? "-" : "" }}{{ item.debit || item.credit }} €
          </div>
        </div>
      </div>
    </div>
    <p class="my-4 text-right underMenu--item">
      Consulter l'historique complet >
    </p>
  </div>
</template>

<style lang='scss'></style>