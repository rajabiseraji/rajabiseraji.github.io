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
              <v-flex xs12 sm4 md3 class="mr-2 my-2" v-for="educationRecord in educationRecords" :key="educationRecord.id">
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
      educationRecords: records.Education,
      lorem: `Lorem ipsum dolor sit amet, mel at clita quando. Te sit oratio vituperatoribus, nam ad ipsum posidonium mediocritatem, explicari dissentiunt cu mea. Repudiare disputationi vim in, mollis iriure nec cu, alienum argumentum ius ad. Pri eu justo aeque torquatos.`
    }
  }
}
</script>

<style>
  .my-container {
    min-height: 100vh;
  }
</style>


