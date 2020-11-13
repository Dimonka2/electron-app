<template>
  <q-menu auto-close>
    <q-list dense>
      <q-item class="GL__menu-link-signed-in">
        <q-item-section>
          <div v-if="logged">Signed in as <strong>{{userName}}</strong></div>
          <div v-if="!logged"><strong>{{userName}}</strong> (Please login)</div>
        </q-item-section>
      </q-item>
      <q-separator />
      <q-item clickable class="GL__menu-link-status">
        <q-item-section>
          <div>
            <q-icon name="tag_faces" color="blue-9" size="18px" />
            Set your status
          </div>
        </q-item-section>
      </q-item>
      <q-separator />
      <q-item clickable class="GL__menu-link">
        <q-item-section>Your profile</q-item-section>
      </q-item>
      <q-item clickable class="GL__menu-link">
        <q-item-section>Your repositories</q-item-section>
      </q-item>
      <q-item clickable class="GL__menu-link">
        <q-item-section>Your projects</q-item-section>
      </q-item>
      <q-item clickable class="GL__menu-link">
        <q-item-section>Your stars</q-item-section>
      </q-item>
      <q-item clickable class="GL__menu-link">
        <q-item-section>Your gists</q-item-section>
      </q-item>
      <q-separator />
      <q-item clickable class="GL__menu-link">
        <q-item-section>Help</q-item-section>
      </q-item>
      <q-item clickable class="GL__menu-link">
        <q-item-section>Settings</q-item-section>
      </q-item>
      <q-item clickable class="GL__menu-link">
        <q-item-section>Sign out</q-item-section>
      </q-item>
    </q-list>
  </q-menu>
</template>

<script>
  import ActiveUser from '../../active-user'
  export default {
    setup() {
      return {
        userName: ActiveUser.userName,
        logged: ActiveUser.loggedIn
      }
    }
  }
</script>
