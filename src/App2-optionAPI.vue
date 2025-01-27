<template>
  <h1>{{ name }}</h1>
  <p v-if="status === 'active'">User is active</p>
  <p v-else-if="status === 'pending'">User is pending</p>
  <p v-else>User is inactive</p>

  <h3>Tasks:</h3>
  <ul>
    <li :key="task" v-for="task in tasks">{{ task }}</li>
  </ul>

  <a :href="link" target="_blink">Click for Google</a>
  <br />
  <button @click="toggleStatus">Change Status</button>
</template>

<script lang="ts">
export default {
  data() {
    return {
      name: 'John Doe',
      status: 'active',
      tasks: ['Task One', 'Taks Two', 'Task Three'],
      link: 'https://www.google.com/',
    }
  },
  methods: {
    toggleStatus() {
      if (this.status === 'active') {
        this.status = 'pendign'
      } else if (this.status === 'pending') {
        this.status = 'inactive'
      } else {
        this.status = 'active'
      }
    },
  },
}
</script>
