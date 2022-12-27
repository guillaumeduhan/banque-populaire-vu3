<script setup>
import { reactive } from "vue";

const state = reactive({
  loading: false,
  open: false,
  textarea: "Bonjour, j'aimerai avoir des informations sur...",
  items: [
    "Mon compte",
    "Demande de rendez-vous",
    "Demande de précision sur Cyberplus",
    "Mes questions sur les produits",
    "Autre",
  ],
});
</script>

<template>
  <div class="concil">
    <div class="concil--box">
      <div class="flex items-start justify-between">
        <div>
          <h3 class="font-bold text-blue-900 text-nowrap">
            Mr Richard Legrand
          </h3>
          <p class="mb-0 mb-1 text-xs description">
            Connecté il y a 12 minutes
          </p>
          <p
            v-if="!state.open"
            @click="state.open = !state.open"
            class="text-sm text-blue-900"
          >
            Contacter
          </p>
        </div>
        <div class="avatar">
          <img src="/richard.png" alt="Conseiller" />
        </div>
      </div>
      <div class="w-full mt-4" v-if="state.open">
        <select class="w-full mb-2">
          <option v-for="(item, index) in state.items" :key="index">
            {{ item }}
          </option>
        </select>
        <textarea v-model="state.textarea" v-html="state.textarea" rows="6" />
        <div class="flex" @click="state.open = !state.open">
          <button class="mr-2 text-sm btn btn-primary">Envoyer</button>
          <p class="underMenu--item">Annuler</p>
        </div>
      </div>
    </div>
  </div>
</template>


<style lang='scss'></style>