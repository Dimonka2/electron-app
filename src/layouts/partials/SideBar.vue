<template>
   <q-scroll-area class="fit">
    <q-list padding v-if="!logged">
      <q-item active clickable v-ripple>
        <q-item-section avatar>
          <q-icon name="person" />
        </q-item-section>

        <q-item-section>
          Login
        </q-item-section>
      </q-item>
    </q-list>
    <q-list padding v-if="logged">
      <q-item clickable v-ripple>
        <q-item-section avatar>
          <q-icon name="person" />
        </q-item-section>

        <q-item-section>
          Inbox
        </q-item-section>
      </q-item>

      <q-item clickable v-ripple>
        <q-item-section avatar>
          <q-icon name="star" />
        </q-item-section>

        <q-item-section>
          Star
        </q-item-section>
      </q-item>

      <q-item clickable v-ripple>
        <q-item-section avatar>
          <q-icon name="send" />
        </q-item-section>

        <q-item-section>
          Send
        </q-item-section>
      </q-item>

      <q-separator />

      <q-item clickable v-ripple>
        <q-item-section avatar>
          <q-icon name="drafts" />
        </q-item-section>

        <q-item-section>
          Drafts
        </q-item-section>
      </q-item>
    </q-list>
  </q-scroll-area>
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
