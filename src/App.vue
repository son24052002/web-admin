<template>
  <v-app>
    <side-bar></side-bar>
    <top-bar></top-bar>

    <v-main>
      <v-container class="py-3 px-6">
          <router-view/>
      </v-container>
    </v-main>
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