<template>
  <h3>History</h3>
  <ul id="list" class="list">
    <li
      v-for="transaction in transactions"
      v-bind:key="transaction.id"
      v-bind:class="transaction.amount < 0 ? 'minus' : 'plus'"
    >
      {{ transaction.text }} <span>£{{ transaction.amount }}</span
      ><button class="delete-btn">x</button>
    </li>
  </ul>
</template>

<script setup>
import { defineProps } from 'vue'

const props = defineProps({
  transactions: {
    type: Array,
    required: true,
  },
})
</script>

<!-- Options API Example below -->
<!-- <script>
export default {
  data() {
    return {
      transactions: [
        { id: 1, text: 'FLower', amount: -19.99 },
        { id: 2, text: 'Salary', amount: 219.97 },
        { id: 3, text: 'Book', amount: -10 },
        { id: 4, text: 'Camera', amount: 150 },
      ],
    }
  },
}
</script> -->

<!-- Composition API Example with explicit setup() function -->
<!-- <script>
export default {
  setup() {
    const transactions = [
      { id: 1, text: 'FLower', amount: -19.99 },
      { id: 2, text: 'Salary', amount: 219.97 },
      { id: 3, text: 'Book', amount: -10 },
      { id: 4, text: 'Camera', amount: 150 },
    ]
    return {
      transactions,
    }
  },
}
</script> -->
