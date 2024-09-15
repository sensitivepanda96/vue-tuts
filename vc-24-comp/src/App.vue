<script>
import {ref} from 'vue';

export default {
  setup() {
    const name = ref('Jonny Dough');
    const status = ref('active');
    const tasks = ref(['four', 'three', 'two', 'one']);
    const link = ref('https://example.com');

    const toggleStatus = () => {
      if (status.value === 'active') {
        status.value = 'pending';
      } else if (status.value === 'pending') {
        status.value = 'inactive';
      } else {
        status.value = 'active';
      }
    }


    return {
      name,
      status,
      tasks,
      link,
      toggleStatus,
    };
  },
};
</script>


<template>
  <h2>Hi, {{ name }}</h2>
  <p v-if="status === 'active'">User {{ name }} is active</p>
  <p v-else-if="status === 'pending'">User {{ name }} is in pending state</p>
  <p v-else>User {{ name }} is inactive</p>

  <h2>Taskies: </h2>
  <ul>
    <li v-for="task in tasks" :key="task">{{ task }}</li>
  </ul>
  <a v-bind:href="link">Click for example</a>
  <br />
  <button v-on:click="toggleStatus">Change Status</button>

</template>