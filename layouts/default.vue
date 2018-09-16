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
          :avatar="item.image ? true : false"
        >
          <v-list-tile-action v-if="!item.image ? true : false">
            <v-icon v-html="item.icon"></v-icon>
          </v-list-tile-action>
          <v-list-tile-avatar size="28" v-else tile>
            <img :src="item.image">
          </v-list-tile-avatar>
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

      <v-btn href="https://github.com/rajabiseraji" target="_blank" icon>
        <v-avatar size="20">
          <img src="/github.svg" alt="g">
        </v-avatar>
      </v-btn>
      <v-btn href="https://www.linkedin.com/in/mohammad-rajabi-b59aa5a3/" target="_blank" icon>
        <v-avatar tile size="20">
          <img src="/linkedin-logo.svg" alt="L">
        </v-avatar>
      </v-btn>
      <v-btn href="https://www.instagram.com/rajabiseraji/" target="_blank" icon>
        <v-avatar tile size="20">
          <img src="/instagram.svg" alt="I">
        </v-avatar>
      </v-btn>
    </v-toolbar>
    <v-content>
      <v-container fill-height>
        <nuxt />
      </v-container>
    </v-content>
    <!-- <v-footer :fixed="true" height="48" app>
      <v-container fill-height>
        <v-layout row align-center fill-height>
          <v-flex xs12 sm10>
            <span class="caption">Coded with &#9825; by rajabiseraji - Using Nuxt and Vuetify</span>
          </v-flex>
          <v-flex>
          <v-spacer></v-spacer>
          </v-flex>
          <v-flex class="text-xs-right" xs12 sm2>
            <span class="caption">&copy; 2018</span>
          </v-flex>
        </v-layout>
      </v-container>
    </v-footer> -->
    <!-- <MyFooter /> -->
  </v-app>
</template>

<script>
import MyFooter from '~/components/MyFooter'
export default {
  components: {
    MyFooter
  },
  data () {
    return {
      bottomNav: 'recent',
      drawer: false,
      items: [
        { icon: 'apps', title: 'Overview', to: '/', image: '/menu.svg' },
        { icon: 'info', title: 'About me', to: '/about', image: '/information.svg' },
        { icon: 'school', title: 'Education', to: '/education', image: '/mortarboard.svg' },
        { icon: 'work', title: 'Experience', to: '/experience', image: '/briefcase.svg' },
        { icon: 'work', title: 'Projects and Research', to: '/projects', image: '/analytics.svg' },
        { icon: 'color_lens', title: 'Skills', to: '/skills', image: '/skills.svg' },
        { icon: 'attach_money', title: 'Honours and Awards', to: '/awards', image: '/cup.svg' },
        { icon: 'attach_money', title: 'Gallery', to: '/gallery', image: '/attach.svg' },
        { icon: 'contacts', title: 'Contact', to: '/contact', image: '/contact.svg' }
      ],
      miniVariant: false,
      title: 'Mohammad Rajabi Seraji'
    }
  }
}
</script>
