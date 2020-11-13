<template>
  <q-page class="row items-center justify-evenly">

    <LoginVue v-if="!logged" />
    <Dashboard v-if="logged" />
  </q-page>
</template>

<script lang="ts">
  import ActiveUser from '../active-user'
  import LoginVue from './auth/Login.vue'
  import Dashboard from './dashboard/Dashboard.vue'

  export default {
    name: 'PageIndex',
    components: { LoginVue , Dashboard},
    setup() {
      return {
        userName: ActiveUser.userName,
        logged: ActiveUser.loggedIn
      }
    },
  }
</script>
