<template>
  <v-footer class="my-footer" height="auto">
    <v-card flat tile class="lighten-1 text-xs-center footer-card">
      <v-card-text class="">
        &copy;2018 — <strong>Built with <span class="red--text">&#9829;</span> using Vue, Nuxt and Vuetify</strong>
        <div>
          <iframe src="https://ghbtns.com/github-btn.html?user=rajabiseraji&repo=rajabiseraji.github.io&type=star&count=true" frameborder="0" scrolling="0" width="90px" height="20px"></iframe>
        </div>
      </v-card-text>
    </v-card>
  </v-footer>
</template>

<script>
export default {

}
</script>

<style scoped>
.my-footer {
  position: fixed;
  right: 0;
  left: 0;
  bottom: 0;
}
.footer-card {
  width: 100%;
}
</style>
