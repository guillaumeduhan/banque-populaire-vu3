<script setup>
import Netflix from "@/components/Icons/Netflix.vue";
import Spotify from "@/components/Icons/Spotify.vue";
import AWS from "@/components/Icons/AWS.vue";
import Navigo from "@/components/Icons/Navigo.vue";

import { reactive } from "vue";
const state = reactive({
  modal: false,
});

const payments = [
  {
    title: "Netflix",
    price: 12.99,
    component: Netflix,
  },
  {
    title: "Spotify",
    price: 15.99,
    component: Spotify,
  },
  {
    title: "AWS",
    price: 36.99,
    component: AWS,
  },
  {
    title: "Navigo",
    price: 84.1,
    component: Navigo,
  },
];

const showModal = () => {
  state.modal = !state.modal;
};
</script>

<template>
  <div class="Payments">
    <Modal v-if="state.modal" @click="showModal" />
    <header>
      <h2 class="font-bold">Paiements automatiques</h2>
      <p class="description">
        Liste de tous les paiements mensuels auxquels vous avez souscrit.
      </p>
    </header>
    <div class="grid grid-cols-4 gap-4">
      <div
        class="Payments--item"
        v-for="(item, index) in payments"
        :key="index"
      >
        <IconsCancel
          class="absolute text-2xl cursor-pointer  icon text-slate-300 hover:text-red-500 right-2 top-2"
          @click="showModal"
        />
        <component class="mb-4 text-3xl text-gray-400" :is="item.component" />
        <p class="mb-2">{{ item.title }}</p>
        <div class="text-sm label">{{ item.price }} €</div>
      </div>
    </div>
  </div>
</template>


<style lang='scss'></style>