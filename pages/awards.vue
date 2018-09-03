<template>
  <v-container fluid fill-height class="my-container">
    <v-layout row wrap fill-height>
      <v-flex xs12>
          <div class="display-2 font-weight-thin mb-3">
              Awards and Honours
          </div>
          <v-divider></v-divider>
      </v-flex>
      <v-flex xs12 class="mt-2">
        <v-layout row wrap justify-space-around>
            <v-flex v-for="award in awardsRecords" :key="award.id" xs12 sm5 class="my-1">
                <v-card>
                    <v-card-media v-if="award.image" :src="award.image" cover height="300px">
                    </v-card-media>
                    <!-- <img v-if="award.image" :src="award.image" :alt="award.title" width="200px"/> -->
                    <v-card-title primary-title>
                    <div>
                        <h3 class="subheading mb-0" v-html="award.title"></h3>
                        <div class="caption grey--text">
                            <span v-html="award.location"></span>
                            <span>{{" | " + award.time}}</span>
                        </div>
                    </div>
                    </v-card-title>

                    <v-card-actions>
                        <v-btn flat color="orange">Link</v-btn>
                        <v-btn flat color="orange">Gallery</v-btn>
                    </v-card-actions>
                </v-card>
            </v-flex>
        </v-layout>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
import records from '~/static/records'
export default {
  data () {
    return {
      awardsRecords: records.Awards
    }
  }
}
</script>

<style>

</style>
