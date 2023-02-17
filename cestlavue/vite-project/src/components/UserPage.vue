<script>
import { reactive } from 'vue';

export default {
  async setup() {
    const state = reactive({
      userList: [],
    });

    async function fetchUsers() {
      const response = await fetch(
        'https://jsonplaceholder.typicode.com/users'
      ).then((response) => response.json());

      return response;
    }

    state.userList = await fetchUsers();

    return {
      state,
      fetchUsers,
    };
  },
};
</script>

<template>
  <main>
    <h1>Users</h1>
    <ul>
      <li v-for="user in state.userList" :key="`user-${user.id}`">
        {{ user.name }} : {{ user.website }}
      </li>
    </ul>
  </main>
</template>

<style>
main {
  display: flex;
  justify-content: center;
  flex-direction: column;
  max-width: 320px;
  margin: 0 auto;
}

main h1 {
  margin-top: 10vh;
  margin-bottom: 20px;
}
</style>
