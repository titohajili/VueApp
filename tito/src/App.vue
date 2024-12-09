<template>

  
  <div class="container">
    
    <Headers/>
    <Balance :total="total" />
    <IncomeExpenses :income="income" :expense="expense"/>
    <TransactionList :transactions="transactions" />
    <AddTransaction/>

</div>

</template>

<script setup>
import Balance from '@/components/Balance.vue';
import Headers from '@/components/Headers.vue';
import IncomeExpenses from '@/components/IncomeExpenses.vue';
import TransactionList from '@/components/TransactionList.vue'
import AddTransaction from '@/components/AddTransaction.vue'

import { ref, computed } from 'vue';
const transactions = ref([
  { id: 1, text: 'Paycheck', amount: 800 },
  { id: 2, text: 'Car Payment', amount: -200 },
  { id: 3, text: 'Groceries', amount: -50 },
  { id: 4, text: 'Gas', amount: -100 },
]);

//Get total
  const total = computed(() => {
    return transactions.value.reduce((acc, transaction) => {
      return acc + transaction.amount;
    }, 0);
  });
  //Get income
  const income = computed(() => {
    return transactions.value
      .filter((transaction) => transaction.amount > 0)
      .reduce((acc, transaction) => {
        return acc + transaction.amount;
      }, 0)
      .toFixed(2);
  });

  //Get expenses
  const expenses = computed(() => {
    return transactions.value
      .filter((transaction) => transaction.amount < 0)
      .reduce((acc, transaction) => {
        return acc + transaction.amount;
      }, 0)
      .toFixed(2);
  });

</script>




<style>


</style>

