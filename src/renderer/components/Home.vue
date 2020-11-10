<template>
  <div id="wrapper">
    <div class="bg-red-600 text-white">
      Test
    </div>
    <a href="#/test">Go to Test</a>
    <btn route="/test">A test</btn>
    <router-view></router-view>
    <system></system>
  </div>
</template>

<script>
  import SystemInformation from './LandingPage/SystemInformation.vue'
  import ButtonVue from './UI/DButton.vue'

  export default {
    name: 'home',
    components: {
      'system': SystemInformation,
      btn: ButtonVue
    }
  }
</script>

<style>

</style>
