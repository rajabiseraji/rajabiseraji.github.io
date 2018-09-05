<template>
    <v-container fluid fill-height class="my-container">
      <v-layout row wrap fill-height>
        <v-flex xs12>
            <div class="display-2 font-weight-thin mb-3">
                Educational Background
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
        <v-flex xs12>
            <v-divider></v-divider>
            <div class="display-2 font-weight-thin mb-3">
                Outstanding Courses
            </div>
            <v-divider></v-divider>
        </v-flex>
        <v-flex xs12>
          <v-layout row wrap>
              <v-flex xs12 class="mr-2 my-2">
                <v-list two-line subheader>
                  <v-list-tile v-for="course in outstandingCourses" :key="course.id" avatar @click="() => openDialog(course)">
                    <v-list-tile-content>
                      <v-list-tile-title>{{ course.title }}</v-list-tile-title>
                      <v-list-tile-sub-title>{{ course.timespan + " - " + course.score}}</v-list-tile-sub-title>
                    </v-list-tile-content>

                    <v-list-tile-action>
                      <v-btn @click="openDialog" icon ripple>
                        <v-icon color="grey lighten-1">info</v-icon>
                      </v-btn>
                    </v-list-tile-action>
                  </v-list-tile>
                </v-list>
              </v-flex>
          </v-layout>
        </v-flex>
        <v-dialog v-model="isOpen" max-width="400">
          <v-card>
            <v-card-title primary-title>
              <div>
                <div class="font-weight-thin headline">{{selectedCourse.title}}</div>
                <div class="gray--text subheading">{{selectedCourse.prof}}</div>
                <span class="gray--text">{{ selectedCourse.timespan}}</span>
                <div class="gray--text"><strong>Course Grade:</strong>{{' ' + selectedCourse.score}}</div>
              </div>
            </v-card-title>
            <v-card-text>
              {{selectedCourse.description}}
            </v-card-text>
          </v-card>
        </v-dialog>
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
      outstandingCourses: records.OutstandingCourses,
      isOpen: false,
      selectedCourse: {},
      lorem: `Lorem ipsum dolor sit amet, mel at clita quando. Te sit oratio vituperatoribus, nam ad ipsum posidonium mediocritatem, explicari dissentiunt cu mea. Repudiare disputationi vim in, mollis iriure nec cu, alienum argumentum ius ad. Pri eu justo aeque torquatos.`
    }
  },
  methods: {
    openDialog: function (course) {
      this.selectedCourse = course
      this.isOpen = true
    }
  }
}
</script>

<style>
  .my-container {
    min-height: 100vh;
  }
</style>


