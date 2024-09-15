<script>
export default {
  data() {
    return {
      name: 'Nigs',
      status: 'pending',
      tasks: ['One', 'Two', 'Three', 'Four'],
      link: 'https://example.com',
    };
  },
  methods: {
    toggleStatus() {
      if (this.status === 'active') {
        this.status = 'pending';
      } else if (this.status === 'pending') {
        this.status = 'inactive';
      } else {
        this.status = 'active';
      }
    },
  },
};
</script>

<template>
  <h2>{{ name }}</h2>
  <p v-if="status === 'active'">User is active</p>
  <p v-else-if="status === 'pending'">User is in pending state</p>
  <p v-else>User is inactive</p>

  <h2>Taskies: </h2>
  <ul>
    <li v-for="task in tasks" :key="task">{{ task }}</li>
  </ul>
  <a v-bind:href="link">Click for example</a>
  <br />
  <button v-on:click="toggleStatus">Change Status</button>

</template>