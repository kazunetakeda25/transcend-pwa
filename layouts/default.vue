<template>
  <v-app>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      fixed
      temporary
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar
      :clipped-left="clipped"
      fixed
      app
      color="primary"
    >
      <v-btn icon color="white">
        <v-icon>mdi-chevron-left</v-icon>
      </v-btn>
      <v-spacer />
      <v-toolbar-title v-text="title" style="color:white;"/>
      <v-spacer />
      <v-app-bar-nav-icon color="white" @click.stop="drawer = !drawer" />
    </v-app-bar>
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
    <v-footer fixed app class="transparent">
      <bottom-navigation />
    </v-footer>
  </v-app>
</template>

<style scoped>
.transparent {
  background-color: transparent !important;
  border-color: transparent !important;
 }
</style>>

<script>
import BottomNavigation from '~/components/BottomNavigation.vue'

export default {
  components: {
    BottomNavigation
  },
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Inspire',
          to: '/inspire'
        }
      ],
      miniVariant: false,
      right: false,
      rightDrawer: false,
      title: 'Jobs For Bid'
    }
  }
}
</script>
