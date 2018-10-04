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
              <div v-if="record.title !== 'LECT'" class="subheading">{{"Professor: " + record.prof}} </div>
              <div v-if="record.duration" class="subheading text--grey">{{"Duration: " + record.duration}} </div>
              <div v-if="record.coLecturer && record.coLecturer !== ''" class="subheading text--grey">{{"Co-lecturer: " + record.coLecturer}} </div>
              <div v-if="record.description" class="subheading font-weight-bold">{{record.title === 'RA' ? 'Job Description' : 'Course Description'}}</div>
              <blockquote class="recordDescription">{{record.description}}</blockquote>
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
      teachingRecords: records.Teaching
    }
  }
}
</script>

<style scoped>
  .v-expansion-panel__header {
    height: fit-content;
  }
  .recordDescription {
    text-align: justify;
  }
</style>
