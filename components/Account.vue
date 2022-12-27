<script setup>
import { computed } from "vue";
import numeral from "numeral";
const props = defineProps({
  account: Object,
});
const account = props.account;

const amount = computed(() => {
  return numeral(account.amount).format("0,0");
});
</script>

<template>
  <div class="Account">
    <img
      v-if="account.icon"
      class="w-12 mr-4 lg:w-auto lg:mr-0 lg:mb-4 lg:h-24"
      :src="account.icon"
    />
    <div class="lg:text-center grow lg:grow-0">
      <h2>{{ account.title }}</h2>
      <p class="price">
        <span :class="account.amount > 0 ? 'text-green-500' : 'text-red-500'">
          {{ amount }} €
        </span>
        <span class="text-sm description">{{
          account.amount_btc ? `soit ${account.amount_btc} BTC` : ""
        }}</span>
      </p>
    </div>
    <div
      v-if="account.last_operation"
      class="text-xs text-right lg:text-center lg:text-sm description"
    >
      <p>Dernière opération:</p>
      <div class="my-1">
        <span class="label mr-1">-{{ account.last_operation.amount }} €</span>
        <span>{{ account.last_operation.date }}</span>
      </div>
    </div>
    <p
      v-if="account.detail"
      class="text-xs text-right lg:text-center lg:text-sm description"
    >
      {{ account.detail }}
    </p>
  </div>
</template>
