<template>
  <div id="wrapper">

    <dnav>
      <dlink title="Test" badge="2" href="#" />
      <dlink title="Testing" badge="3" />
    </dnav>

    <btn route="/test" shadow="md">A test</btn>

    <router-view></router-view>

    <div class="grid grid-cols-1 gap-4 md:grid-cols-2">
      <div>
        <tabs class="m-3">
          <tab name="Services" badge="2">
            <h1>What we do</h1>
          </tab>
          <tab name="Pricing" :selected="true">
            <h1>How much we do it for</h1>
          </tab>
          <tab name="About Us">
            <h1>Why we do it</h1>
          </tab>
        </tabs>
      </div>
      <div>
        <card class="m-4" shadow="xl" >
          <template v-slot:title>
            System information
          </template>
          <template v-slot:tools>
            <btn>test</btn>
          </template>
          <system></system>
          <template v-slot:footer>
            <btn>test</btn>
          </template>
        </card>
      </div>
    </div>
  </div>
</template>

<script>
  import SystemInformation from './LandingPage/SystemInformation.vue'
  import ButtonVue from './UI/DButton.vue'
  import DHeaderVue from './UI/DHeader.vue'
  import DLinkVue from './UI/DLink.vue'
  import DTabVue from './UI/DTab.vue'
  import DTabsVue from './UI/DTabs.vue'
  import UiCard from './UI/UICard.vue'

  export default {
    name: 'home',
    components: {
      'system': SystemInformation,
      btn: ButtonVue,
      card: UiCard,
      tabs: DTabsVue,
      tab: DTabVue,
      dnav: DHeaderVue,
      dlink: DLinkVue
    }
  }
</script>

<style>

</style>
