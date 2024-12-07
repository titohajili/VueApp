<template>

  
  <div class="container">
    
    <Headers/>
    <Balance :total="total" />
    <IncomeExpenses/>
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

  const total = computed(() => {
    return transactions.value.reduce((acc, transaction) => {
      return acc + transaction.amount;
    }, 0);
  });


</script>




<style>


</style>

