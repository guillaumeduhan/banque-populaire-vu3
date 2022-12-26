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
    <img v-if="account.icon" class="h-24 mb-4" :src="account.icon" />
    <h2>{{ account.title }}</h2>
    <p class="price">
      <span :class="account.amount > 0 ? 'text-green-500' : 'text-red-500'">
        {{ amount }} €
      </span>
      <span class="text-sm description">{{
        account.amount_btc ? `soit ${account.amount_btc} BTC` : ""
      }}</span>
    </p>
    <div v-if="account.last_operation" class="text-sm text-center description">
      <p>Dernière opération:</p>
      <div>
        <span class="label">-{{ account.last_operation.amount }} €</span>
        {{ account.last_operation.date }}, {{ account.last_operation.title }}
      </div>
    </div>
    <p v-if="account.detail" class="text-sm text-center description">
      {{ account.detail }}
    </p>
  </div>
</template>