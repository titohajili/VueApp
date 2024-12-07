<template>
  <TransactionHistory
    :transactions="transactions"
    @deleteTransaction="handleDelete"
  />
</template>

<script setup>
import TransactionHistory from './TransactionHistory.vue';
import { ref } from 'vue';

const transactions = ref([
  { id: 1, text: 'Salary', amount: 500 },
  { id: 2, text: 'Groceries', amount: -50 },
  { id: 3, text: 'Car Repair', amount: -150 },
]);

const handleDelete = (id) => {
  transactions.value = transactions.value.filter((transaction) => transaction.id !== id);
};
</script>
