<template>
    <v-container fluid fill-height class="my-container">
      <v-layout row wrap fill-height>
        <v-flex xs12>
            <div class="display-2 font-weight-thin mb-3">
                Projects and Research
            </div>
            <v-divider></v-divider>
        </v-flex>
        <v-flex class="mt-4" xs12>
            <div class="headline font-weight-thin mb-1">
                Research
            </div>
            <v-divider></v-divider>
        </v-flex>
        <v-flex xs12 class="mt-2">
          <ProjectItem :projectItem="projectItem"
                        v-for="projectItem in projectRecords" 
                        :key="projectItem.id" />
        </v-flex>
        <v-flex xs12>
            <div class="headline font-weight-thin mb-1">
                Projects
            </div>
            <v-divider></v-divider>
        </v-flex>
        <v-flex xs12 class="mt-2">
          <ProjectItem :projectItem="researchItem"
                        v-for="researchItem in researchRecords" 
                        :key="researchItem.id" />
        </v-flex>
      </v-layout>
    </v-container>
</template>

<script>
import ProjectItem from '~/components/ProjectItem'
import records from '~/static/records.json'
export default {
  components: {
    ProjectItem
  },
  data () {
    return {
      projectRecords: records.Projects.Research,
      researchRecords: records.Projects.Projects
    }
  }
}
</script>

<style>

</style>
