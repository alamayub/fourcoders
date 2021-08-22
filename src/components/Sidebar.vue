<template>
  <v-navigation-drawer v-model="drawer" app mobile-breakpoint="10024" color="primary" dark>
    <v-list nav dense shaped class="pl-0">
      <v-list-item-group v-model="selectedItem" color="white">
        <v-list-item v-for="(menu, i) in menus" :key="i" :to="menu.to">
          <v-list-item-icon class="mr-1 ml-2">
            <v-icon size="16">{{ menu.icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title v-text="menu.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list-item-group>
    </v-list> 
  </v-navigation-drawer>  
</template>

<script>
export default {
  data: () => ({
    menus: [
      { title: 'Home', icon: 'mdi-home', to: '/' },
      { title: 'Services', icon: 'mdi-cog', to: '/services' },
      { title: 'Portfolio', icon: 'mdi-bag-personal', to: '/portfolio' },
      { title: 'About Us', icon: 'mdi-account', to: '/about' },
      { title: 'Our Team', icon: 'mdi-account-multiple', to: '/team' },
      { title: 'Contact Us', icon: 'mdi-account-box', to: '/contact' },
      { title: 'Career', icon: 'mdi-handshake', to: '/career' } 
    ],
    selectedItem: 1, 
  }),
  computed: {
    drawer: {
      get () {
        return this.$store.state.drawer
      },
      set (val) {
        this.$store.commit('SET_DRAWER', val)
      },
    },
  }
}
</script>