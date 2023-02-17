<script>
export default {
  data: () => ({
    userList: [1, 2, 3],
  }),
  methods: {
    async fetchUsers() {
      this.userList = await fetch(
        'https://jsonplaceholder.typicode.com/users'
      ).then((response) => response.json());
    },
  },
  created() {
    this.fetchUsers();
  },
};
</script>

<template>
  <main>
    <h1>Users</h1>
    <ul>
      <li v-for="user in userList" :key="`user-${user.id}`">
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
