<template>
  <v-app>
    <side-bar></side-bar>
    <top-bar></top-bar>
  </v-app>
</template>

<script>
import SideBar from './components/SideBar.vue'
import TopBar from './components/TopBar.vue'
export default {
  components: { SideBar, TopBar },

}
</script>

<style>

</style>