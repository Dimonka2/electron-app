<template>
  <q-layout  view="hHh Lpr lff" container class="" style="height: 100vh;">
    <q-header elevated class="text-white" style="background: #24292e" >
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="drawer = !drawer"
        />

        <q-toolbar-title>
          LitReview app
        </q-toolbar-title>

        <q-btn dense flat no-wrap class="m-l-2">
              Menu
            <q-icon name="arrow_drop_down" size="16px" />
            <UserMenuVue />

          </q-btn>
      </q-toolbar>
    </q-header>

    <q-drawer
        v-model="drawer"
        show-if-above

        :mini="miniState"
        @mouseover="miniState = false"
        @mouseout="miniState = true"
        mini-to-overlay

        :width="200"
        :breakpoint="500"
        bordered
        content-class="bg-grey-3"
      >
        <SideBarVue />
      </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script lang="ts">
import EssentialLink from 'components/EssentialLink.vue'
import UserMenuVue from './partials/UserMenu.vue'

import { defineComponent, ref } from '@vue/composition-api';
import SideBarVue from './partials/SideBar.vue';

export default defineComponent({
  name: 'MainLayout',
  components: {
    EssentialLink,
    UserMenuVue,
    SideBarVue
  },
  setup() {

    // console.log('Show what is imported', linksData)

    const leftDrawerOpen = ref(false);

    return {leftDrawerOpen, drawer: false, miniState: true}
  }
});
</script>
