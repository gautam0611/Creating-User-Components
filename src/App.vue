<template>
  <section>
    <active-user v-for="user in users" :key="user.id" :id="user.id" :username="user.name" :age="user.age"
      @delete="removeUser">
    </active-user>
    <user-data @set-data="setTheData"></user-data>
  </section>
</template>

<script>
export default {
  data() {
    return {
      users: [
        {
          id: "G",
          name: 'Gautam Narayan',
          age: 23
        }
      ]
    }
  },
  methods: {
    setTheData(name, age) {
      const newUser = {
        id: new Date().toISOString(),
        name: name,
        age: age,
      }
      this.users.push(newUser);
    },
    removeUser(userID) {
      this.users = this.users.filter((user) => user.id !== userID)
    }
  }

}
</script>

<style>
html {
  font-family: sans-serif
}

section {
  margin: 2rem auto;
  max-width: 40rem;
  border-radius: 5px;
  border: 1px solid #ccc;
  padding: 1rem;
}
</style>