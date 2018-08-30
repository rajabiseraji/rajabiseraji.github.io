<template>
    <v-card class="my-card pt-4">
        <v-card-media
          contain
          v-if="educationRecord.logo === '/aut.jpg'"
          src="/aut.jpg"
          height="120px"
        />
        <v-card-media
          contain
          v-else
          src="/alborz.jpg"
          height="120px"
        />

        <v-card-title primary-title>
          <div>
            <div class="headline">{{educationRecord.titleDescription}}</div>
            <span class="grey--text">{{educationRecord.location + ' - ' + educationRecord.timespan}}</span>
          </div>
        </v-card-title>

        <v-card-text>
          <p>
              {{educationRecord.major}}<br>
              <span v-if="educationRecord.minor">{{educationRecord.minor}}<br></span>
              {{educationRecord.GPA}}
          </p>
        </v-card-text>

        <v-card-actions class="my-card-actions">
          <v-btn flat>Website</v-btn>
          <v-btn flat color="indigo">Gallery</v-btn>
          <v-spacer></v-spacer>
        </v-card-actions>

      </v-card>
</template>

<script>
export default {
  props: {
    educationRecord: Object
  },
  data () {
    return {
      show: false
    }
  }

}
</script>

<style>
</style>
