<template>
  <div id="wrapper">
    <div class="bg-red-600 text-white">
      Test
    </div>
    <a href="#/test">Go to Test</a>
    <btn route="/test">A test</btn>
    <router-view></router-view>
    <card class="m-4">

      <system></system>
    </card>
  </div>
</template>

<script>
  import SystemInformation from './LandingPage/SystemInformation.vue'
  import ButtonVue from './UI/DButton.vue'
  import UiCard from './UI/UICard.vue'

  export default {
    name: 'home',
    components: {
      'system': SystemInformation,
      btn: ButtonVue,
      card: UiCard
    }
  }
</script>

<style>

</style>
