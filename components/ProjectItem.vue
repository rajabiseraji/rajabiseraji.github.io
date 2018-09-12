<template>
<v-layout row>
  <v-card class="mr-2 mb-2" width="100%">
    <v-layout row wrap class="w-100">
      <v-flex class="img-section" xs12 sm4 justify-center align-center>
        <div>
          <img :src="projectItem.logo" height="150px" />
        </div>
      </v-flex>
      <v-flex xs12 sm8>
        <v-card-title>
          <div>
            <span class="headline">{{projectItem.title}}</span><br>
            <span class="subheading">{{projectItem.location}}</span>
            <div class="subheading" v-if="projectItem.course">
              <strong>Course:</strong>
              {{' ' + projectItem.course}}
            </div>
            <div class="grey--text caption">{{projectItem.duration}}</div><br>
          </div>
        </v-card-title>
        <v-card-text>
          <p>{{projectItem.description}}</p>
        </v-card-text>
        <v-card-actions v-if="projectItem.links">
          <v-btn v-for="link in projectItem.links" :key="link.id" flat dark class="black" :href="link.url" target="_blank">
            <v-avatar v-if="link.logo" size="20" class="mr-2">
              <img :src="link.logo" alt="g">
            </v-avatar>
            {{link.title}}
          </v-btn>
        </v-card-actions>
      </v-flex>
    </v-layout>
  </v-card>
</v-layout>
</template>

<script>
export default {
  props: {
    projectItem: Object
  }
}
</script>

<style scoped>
  .my-card {
    width: 300px;
  }
  .img-section {
    display: flex;
  }
</style>
