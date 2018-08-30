<template>
    <v-container fluid fill-height class="my-container">
      <v-layout row wrap fill-height>
        <v-flex xs12>
            <div class="display-2 font-weight-thin mb-3">
                Education
            </div>
            <v-divider></v-divider>
        </v-flex>
        <v-flex xs12>
          <v-layout row wrap>
              <v-flex xs12 sm5 md3 class="mr-2" v-for="educationRecord in educationRecords" :key="educationRecord.id">
                  <EducationItem :educationRecord="educationRecord" />
              </v-flex>
          </v-layout>
        </v-flex>
      </v-layout>
    </v-container>
</template>

<script>
import records from '~/static/records.json'
import EducationItem from '~/components/EducationItem'
export default {
  components: {
    EducationItem
  },
  data () {
    return {
      educationRecords: records.Education
    }
  }
}
</script>

<style>
  .my-container {
    height: 100vh;
  }
</style>


