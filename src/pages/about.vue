<template>
  <!-- users list (all) -->
  <section>
    <h1>Все пользователи:</h1>
    <ul>
      <li v-for="user in getUsers" :key="user.id">
        <p>{{ user.id }}</p>
        <p>{{ user.name }}</p>
        <p>{{ user.admin ? 'Это админ' : 'Обычный юзер' }}</p>
      </li>
    </ul>
  </section>
  <!-- count users -->
  <section>
    <p>{{ getUsersLength }}</p>
  </section>
</template>

<script>
export default {
  computed: {
    user() {
      return this.$store.getters.getUser
    },
    getUsers() {
      return this.$store.getters.getAllUsers
    },
    getUsersLength() {
      return this.$store.getters.getUsersLength
    }
  }
}
</script>
