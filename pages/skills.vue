<template>
  <v-container fluid fill-height class="my-container">
    <v-layout row wrap fill-height>
      <v-flex xs12>
          <div class="display-2 font-weight-thin mb-3">
              Skills
          </div>
          <v-divider></v-divider>
      </v-flex>
      <v-flex xs12 class="my-2">
        <v-btn v-for="skillList in skillRecords" :href="'#'+skillList.id" :key="skillList.id" class="mx-1 pa-2 navButtons" color="primary">{{skillList.title}}</v-btn>
      </v-flex>
      <v-flex xs12 class="mt-2">
        <SkillItem v-for="skillList in skillRecords" 
                  :id="skillList.id"
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

<style scoped>
  .navButtons { 
    font-size: 0.75rem;
  }
</style>
