<template>
  <v-app-bar color="white" app height="80" elevate-on-scroll>
    <v-container class="d-flex justify-space-between align-center pa-0">
      <div class="logo" style="height: 50px;">
        <img src="../assets/logo.png" alt="Logo">  
      </div>
      <v-app-bar-nav-icon @click.stop="setDrawer(!drawer)" class="white d-block d-sm-block d-md-none" />
      <div class="d-none d-sm-none d-md-block nav">
        <v-btn text active-class="active__nav" tile v-for="(menu, m) in menus" :key="m" :to="menu.to">
          <v-icon left size="16">{{ menu.icon }}</v-icon>
          <span>{{ menu.title }}</span>
        </v-btn>
      </div>
    </v-container>  
  </v-app-bar>  
</template>

<script>
import { mapState, mapMutations } from 'vuex'
export default {
  data: () => ({
    selectedItem: 0,
    menus: [
      { title: 'Home', icon: 'mdi-home', to: '/' },
      { title: 'Services', icon: 'mdi-bag-personal', to: '/services' },
      { title: 'Portfolio', icon: 'mdi-cog', to: '/portfolio' },
      { title: 'About Us', icon: 'mdi-account', to: '/about' },
      { title: 'Our Team', icon: 'mdi-account-multiple', to: '/team' },
      { title: 'Contact Us', icon: 'mdi-account-box', to: '/contact' },
      { title: 'Career', icon: 'mdi-handshake', to: '/career' } 
    ],
  }),
  computed: {
    ...mapState(['drawer']),
  },
  methods: {
    ...mapMutations({
      setDrawer: 'SET_DRAWER',
    }),
  },
}
</script>

<style scoped>
.nav .theme--light.v-btn--active:hover::before, .nav .theme--light.v-btn--active::before { opacity: 0 !important; }
.nav .v-btn { height: 80px !important; }
.active__nav {
  border-bottom: 3px solid #1976d2;
  color: #1976d2 !important;
  font-weight: 400 !important;
}
.f_active_nav {
  color: #fff !important;
  border-bottom: 3px solid #fff;
  font-weight: 400 !important;
}
</style>