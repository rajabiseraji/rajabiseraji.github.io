<template>
    <v-expansion-panel
      expand
    >
      <v-expansion-panel-content
        v-for="record in executiveRecords"
        :key="record.id"
      >
        <div slot="header">
            <v-layout row wrap>
                <v-flex v-if="record.logo" xs12 sm2 justify-center>
                    <v-avatar tile>
                        <img :src="record.logo" :alt="record.title"/>
                    </v-avatar>
                </v-flex>
                <v-flex xs12 sm10>
                    <div class="subheading"><span>{{record.titleDescription + " | "}}</span><span v-html="record.location"></span></div>
                    <div class="caption">{{record.timespan}} </div>
                </v-flex>
            </v-layout>
        </div>
        <v-card>
          <v-card-text class="grey lighten-5">
              <div class="heading font-weight-bold" v-if="record.firstJob">{{record.firstJob}}</div>
              <blockquote >{{record.description || record.firstJobDesc}}</blockquote>
              <div class="secondJob mt-1" v-if="record.secondJob">
                <div class="heading font-weight-bold" v-if="record.secondJob">{{record.secondJob}}</div>
                <blockquote >{{record.secondJobDesc}}</blockquote>
              </div>
              <div class="mt-3" v-if="record.links && record.links.length !== 0">
                <div class="subheading font-weight-bold">Links</div>
                <v-divider></v-divider>
                <div class="mt-2" v-for="link in record.links" :key="link.id">
                  <a target="_blank" :href="link.linkURL || link.url">{{link.linkText || link.title}}</a>
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
      executiveRecords: records.Executive
    }
  }
}
</script>

<style>
  .v-expansion-panel__header {
    height: fit-content;
  }
</style>
