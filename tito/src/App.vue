<template>

  <Headers/>
  <Balance/>
  <income-expenses/>
  <TransactionList/>
  <AddTransaction/>

<div class="container">


</div>

</template>

<script>
import Balance from '@/components/Balance.vue';
import Headers from '@/components/Headers.vue';
import IncomeExpenses from '@/components/IncomeExpenses.vue';
import TransactionList from '@/components/TransactionList.vue'
import AddTransaction from '@/components/AddTransaction.vue'


export default {

     name: "AppHeader",
    
    components: {
        Headers,
        Balance,
        IncomeExpenses,
        TransactionList,
        AddTransaction
    },
}

</script>




<style>


</style>

