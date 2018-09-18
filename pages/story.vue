<template>
  <v-layout row wrap fill-height>
    <v-flex xs12>
        <div class="display-2 font-weight-thin mb-3">
            My Story
        </div>
        <v-divider></v-divider>
        <v-layout row wrap>
          <v-flex xs12 v-for="(storyPart, index) in storyParts" :key="storyPart.id" class="pt-0 mt-3 body-2">
            <v-layout row wrap :reverse="index%2 === 0">
              <v-flex d-flex justify-center align-center xs12 sm3 v-if="index > 2 && storyPart.photo" class="story-image my-2">
                <img height="150px" :src="storyPart.photo" alt="image">
              </v-flex>
              <v-flex xs12 sm9 v-if="index > 2" d-flex justify-center align-center class="story-text font-weight-regular">{{storyPart.text}}</v-flex>
              <v-flex xs12 v-else class="font-weight-thin verses">{{storyPart.text}}</v-flex>
            </v-layout>
            <div class="mb-5" v-if="index === 2"></div>
          </v-flex>  
        </v-layout>
    </v-flex>
    <v-flex xs12>
      
    </v-flex>
  </v-layout>
</template>

<script>
import records from '~/static/records.json'
export default {
  data () {
    return {
      storyParts: records.Story
    }
  }
}
</script>

<style scoped>
.story-image {
  display: flex;
  width: 100%;
  justify-content: center;
  align-items: center;
}
.verses {
  text-align: center;
  line-height: 1;
  font-size: 1.5rem;
}
.story-text {
  text-align: justify;
}
</style>
