<template>
  <v-container fluid fill-height class="my-container">
    <v-layout row wrap>
      <v-flex xs12>
        <div class="display-2 font-weight-thin mb-3">
            Experience and Background
        </div>
        <v-divider></v-divider>
      </v-flex>
      <v-flex xs12 fill-height class="mt-2">
      <v-tabs
          centered
          color="primary"
          dark
          icons-and-text
          grow
      >
        <v-tabs-slider color="yellow"></v-tabs-slider>

        <v-tab href="#tab-1">
          <span class="mt-2">Teaching</span>
          <img height="30px" src="/education.svg" alt="Teaching"/>
        </v-tab>

        <v-tab href="#tab-2">
          <span class="mt-2">Industry</span>
          <img height="30px" src="/programmer.svg" alt="Industry">
        </v-tab>

        <v-tab href="#tab-3">
          <span class="mt-2">Executive</span>
          <img height="30px" src="/team.svg" alt="Executive">
        </v-tab>

        <v-tab-item
        v-for="i in 3"
        :id="'tab-' + i"
        :key="i"
        >
          <v-card flat>
            <v-card-text>{{ text }}</v-card-text>
          </v-card>
        </v-tab-item>
      </v-tabs>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  data () {
    return {
      text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'
    }
  }
}
</script>

<style>

</style>
