<template>
  <div id="wrapper">
    <div class="bg-red-600 text-white">
      Test
    </div>
    <btn route="/test">A test</btn>

    <router-view></router-view>


    <tabs>
      <tab name="Services" :selected="true">
        <h1>What we do</h1>
      </tab>
      <tab name="Pricing">
        <h1>How much we do it for</h1>
      </tab>
      <tab name="About Us">
        <h1>Why we do it</h1>
      </tab>
    </tabs>


    <card class="m-4">
      <template v-slot:title>
        System information
      </template>
      <template v-slot:tools>
        <btn>test</btn>
      </template>
      <system></system>
    </card>


  </div>
</template>

<script>
  import SystemInformation from './LandingPage/SystemInformation.vue'
  import ButtonVue from './UI/DButton.vue'
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
      tab: DTabVue
    }
  }
</script>

<style>

</style>
