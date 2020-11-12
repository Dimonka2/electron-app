<template>
  <q-layout class="q-pa-md">
    <q-header elevated class="text-white" style="background: #24292e" height-hint="61.59">
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
            <user-menu></user-menu>

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
        <q-scroll-area class="fit">
          <q-list padding>
            <q-item clickable v-ripple>
              <q-item-section avatar>
                <q-icon name="inbox" />
              </q-item-section>

              <q-item-section>
                Inbox
              </q-item-section>
            </q-item>

            <q-item active clickable v-ripple>
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
      </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script lang="ts">
import EssentialLink from 'components/EssentialLink.vue'
import UserMenuVue from 'components/UserMenu.vue'

import { defineComponent, ref } from '@vue/composition-api';
import linksData from '../store/side-menu'

export default defineComponent({
  name: 'MainLayout',
  components: {
    EssentialLink,
    'user-menu': UserMenuVue
  },
  setup() {

    // console.log('Show what is imported', linksData)

    const leftDrawerOpen = ref(false);
    const essentialLinks = ref(linksData.menu);

    return {leftDrawerOpen, essentialLinks, drawer: false, miniState: true}
  }
});
</script>
