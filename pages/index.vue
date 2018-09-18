<template>
  <v-layout row fill-height align-center wrap>
    <v-flex xs12 sm6 md4>
      <div class="text-xs-center">
        <v-avatar
          :size="200"
          color="grey lighten-4"
          class="mb-3 elevation-2"
        >
          <img src="/moh3.png" alt="avatar">
        </v-avatar>
      </div>
    </v-flex>
    <v-flex xs12 sm6 md8 class="pb-5">
      <v-layout column fill-height justify-center>
        <v-flex xs12>
          <div class="display-3 name-title">
            {{name}}
          </div> 
        </v-flex>
        <v-flex xs6 justify-start>
          <div class="sub-heading">{{overview}}</div>
        </v-flex>
      </v-layout>
    </v-flex>
    <MyFooter></MyFooter>
  </v-layout>
</template>

<script>
import records from '~/static/records.json'
import MyFooter from '~/components/MyFooter'
export default {
  components: {
    MyFooter
  },
  data () {
    return {
      name: records.Name,
      overview: records.Overview
    }
  }
}
</script>

<style scoped>
  .name-title {
    font-weight: 100;
  }
</style>


