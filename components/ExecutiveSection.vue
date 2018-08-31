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
              <blockquote >{{record.description || record.firstJobDesc}}</blockquote>
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
