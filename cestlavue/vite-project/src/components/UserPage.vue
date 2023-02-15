<script>
// export default {
//   data: () => ({
//     users: [],
//   }),
//   methods: {
//     async fetchUsers() {
//       this.users = await fetch(
//         "https://jsonplaceholder.typicode.com/users"
//       ).then((response) => response.json());
//     },
//   },
//     created() {
//         this.fetchUsers()
//         console.log("Hello")
//     }
//   },

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
    <pre>{{ userList }}</pre>
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
