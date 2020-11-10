<template>
  <div id="wrapper">
    <div class="bg-red-600 text-white">
      Test page
    </div>
    <btn color="success" route="/" cls="m-2" >Back to home <badge color="red-200 text-red-600">2</badge></btn>

    <router-view></router-view>
  </div>
</template>

<script>
  import DButton from './UI/DButton.vue'
  import DBadgeVue from './UI/DBadge.vue'

  export default {
    name: 'test',
    components: {
      btn: DButton,
      badge: DBadgeVue
    }
  }
</script>

<style>

</style>