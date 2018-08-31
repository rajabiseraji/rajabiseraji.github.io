<template>
    <v-expansion-panel
      expand
    >
      <v-expansion-panel-content
        v-for="record in teachingRecords"
        :key="record.id"
      >
        <div slot="header">
          <div class="subheading">{{record.titleDescription + " | " + record.course}}</div>
          <div class="caption">{{record.timespan + " - " + record.location}} </div>
        </div>
        <v-card>
          <v-card-text class="grey lighten-5">
              <blockquote >{{record.description}}</blockquote>
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
      teachingRecords: records.Teaching
    }
  }
}
</script>

<style>
  .v-expansion-panel__header {
    height: fit-content;
  }
</style>
