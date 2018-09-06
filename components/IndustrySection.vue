<template>
    <v-expansion-panel
      expand
    >
      <v-expansion-panel-content
        v-for="record in industryRecords"
        :key="record.id"
      >
        <div slot="header">
            <v-layout row wrap>
                <v-flex xs12 sm2 justify-center d-flex>
                    <v-avatar class="avatar-class" tile>
                        <img class="company-logo" :src="record.logo" :alt="record.title"/>
                    </v-avatar>
                </v-flex>
                <v-flex xs12 sm10>
                    <div class="subheading">{{record.titleDescription + " | " + record.location}}</div>
                    <div class="caption">{{record.timespan}} </div>
                </v-flex>
            </v-layout>
        </div>
        <v-card>
          <v-card-text class="grey lighten-5">
              <div class="font-weight-bold grey--text subheading">Job Description</div>
              <blockquote >{{record.description || record.firstJobDesc}}</blockquote>
              <div class="mt-3" v-if="record.links && record.links.length !== 0">
                <div class="subheading font-weight-bold">Links</div>
                <v-divider></v-divider>
                <div class="mt-2" v-for="link in record.links" :key="link.id">
                  <a :href="link.url">{{link.title}}</a>
                </div>
              </div>
          </v-card-text>
        </v-card>
      </v-expansion-panel-content>
    </v-expansion-panel>
</template>

<script>
import records from '~/static/records.json'
export default {
  data () {
    return {
      industryRecords: records.Working
    }
  }
}
</script>

<style scoped>
  .v-expansion-panel__header {
    height: fit-content;
  }
</style>
