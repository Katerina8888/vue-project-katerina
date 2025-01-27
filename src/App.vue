<template>
  <h1>{{ name }}</h1>
  <p v-if="status === 'active'">User is active</p>
  <p v-else-if="status === 'pending'">User is pending</p>
  <p v-else>User is inactive</p>

  <h3>Tasks:</h3>
  <ul>
    <li :key="task" v-for="task in tasks">{{ task }}</li>
  </ul>

  <br />
  <button @click="toggleStatus">Change Status</button>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const name = ref('John Doe')
const status = ref('active')
const tasks = ref(['Task One', 'Task Two', 'Task Three'])
const toggleStatus = () => {
  if (status.value === 'active') {
    status.value = 'pendign'
  } else if (status.value === 'pending') {
    status.value = 'inactive'
  } else {
    status.value = 'active'
  }
}
</script>
