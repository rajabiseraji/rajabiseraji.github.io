<template>
  <v-container fluid fill-height class="my-container">
    <v-layout row wrap fill-height>
      <v-flex xs12>
          <div class="display-2 font-weight-thin mb-3">
              Skills
          </div>
          <v-divider></v-divider>
      </v-flex>
      <v-flex xs12 class="mt-2">
        <SkillItem v-for="skillList in skillRecords" 
                  :key="skillList.id" 
                  :image="skillList.image"
                  :title="skillList.title" 
                  :skills="skillList.skills" />
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
import SkillItem from '~/components/SkillItem'
import records from '~/static/records'
export default {
  components: {
    SkillItem
  },
  data () {
    return {
      skillRecords: records.Skills
    }
  }
}
</script>

<style>

</style>
