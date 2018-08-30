<template>
  <v-app class="gray--lighten-2">
    <v-navigation-drawer
      :mini-variant.sync="miniVariant"
      :clipped="true"
      v-model="drawer"
      fixed
      app
    >
      <v-list>
        <v-list-tile
          router
          :to="item.to"
          :key="i"
          v-for="(item, i) in items"
          exact
        >
          <v-list-tile-action>
            <v-icon v-html="item.icon"></v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title v-text="item.title"></v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar fixed app color="primary" dark :clipped-left="true">
      <v-toolbar-side-icon @click="drawer = !drawer"></v-toolbar-side-icon>
      <v-toolbar-title v-text="title" class="font-weight-light"></v-toolbar-title>
      <v-spacer></v-spacer>
    </v-toolbar>
    <v-content>
      <v-container fill-height>
        <nuxt />
      </v-container>
    </v-content>
    <v-footer :fixed="true" height="48" app>
      <v-container fill-height>
        <v-layout row align-center fill-height>
          <v-flex xs12 sm10>
            <span>Coded with &#9825; by rajabiseraji - Using Nuxt and Vuetify</span>
          </v-flex>
          <v-flex>
          <v-spacer></v-spacer>
          </v-flex>
          <v-flex class="text-xs-right" xs12 sm2>
            <span>&copy; 2018</span>
          </v-flex>
        </v-layout>
      </v-container>
    </v-footer>
  </v-app>
</template>

<script>
  export default {
    data () {
      return {
        bottomNav: 'recent',
        drawer: false,
        items: [
          { icon: 'apps', title: 'Overview', to: '/' },
          { icon: 'info', title: 'About me', to: '/about' },
          { icon: 'school', title: 'Education', to: '/education' },
          { icon: 'work', title: 'Experience', to: '/experience' },
          { icon: 'color_lens', title: 'Skills', to: '/skills' },
          { icon: 'attach_money', title: 'Honours and Awards', to: '/awards' },
          { icon: 'contacts', title: 'Contact', to: '/contact' }
        ],
        miniVariant: false,
        title: 'Mohammad Rajabi Seraji'
      }
    }
  }
</script>
