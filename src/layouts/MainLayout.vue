<template>
  <div class="app-main-layout">
    <Navbar @click="isOpen = !isOpen"></Navbar>
    <Sidebar v-model="isOpen"></Sidebar>

    <main class="app-content" :class="{full: !isOpen}">
      <div class="app-page">
       <router-view />
      </div>
    </main>

    <div class="fixed-action-btn">
      <router-link to="/record" class="btn-floating btn-large blue" href="#">
        <i class="large material-icons">add</i>
      </router-link>
    </div>
  </div>
</template>

<script>
import Navbar from "@/components/app/Navbar.vue";
import Sidebar from "@/components/app/Sidebar.vue";
export default {
  name: 'main-layout',
  components: {
    Navbar,
    Sidebar
  },
  data() {
    return {
      isOpen: true
    }
  },
}
</script>
