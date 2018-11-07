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

      <v-btn color="transparent" href="/CV.zip" target="_blank">
        <strong>CV</strong>
      </v-btn>
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
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      bottomNav: 'recent',
      drawer: false,
      items: [
        { icon: 'apps', title: 'Overview', to: '/', image: '/menu.svg' },
        { icon: 'info', title: 'About me', to: '/story', image: '/information.svg' },
        { icon: 'school', title: 'Education', to: '/education', image: '/mortarboard.svg' },
        { icon: 'work', title: 'Experience', to: '/experience', image: '/briefcase.svg' },
        { icon: 'work', title: 'Projects and Research', to: '/projects', image: '/analytics.svg' },
        { icon: 'color_lens', title: 'Skills', to: '/skills', image: '/skills.svg' },
        { icon: 'attach_money', title: 'Honours and Awards', to: '/awards', image: '/cup.svg' },
        // { icon: 'attach_money', title: 'Gallery', to: '/gallery', image: '/attach.svg' },
        { icon: 'contacts', title: 'Contact', to: '/contact', image: '/contact.svg' },
        { icon: 'contacts', title: 'About This Site', to: '/about', image: '/question.svg' }
      ],
      miniVariant: false,
      title: 'Mohammad Rajabi Seraji'
    }
  }
}
</script>
