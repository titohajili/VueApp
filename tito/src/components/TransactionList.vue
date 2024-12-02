<template>

<h3>History</h3>
      <ul id="list" class="list">
        <ul class="list" id="list">
          {{ transaction.text }}
          <li class="minus">
          Cash <span>{{transaction.amount}}</span>
          
          <button class="delete-btn">x</button>
        </li>

      </ul>

        <!-- 

        <li class="plus">
          Paycheck <span>$800</span><button class="delete-btn">x</button>
        </li> -->

      </ul>

</template>

<script>



export default {
  data(){
     return {
       transactions: [
        {id: 1, text: 'Flower', amount: -19.99},
        {id: 2, text: 'Salary', amount: 3000}, 
        {id: 3, text: 'Book', amount: -10},
        {id: 4, text: 'Camera', amount: 150}
       ]
     }
  }
}

</script>