<template>
  <v-layout row wrap fill-height>
      <v-flex xs12>
          <div class="display-2 font-weight-thin mb-3">
              Contact
          </div>
          <v-divider></v-divider>
      </v-flex>
      <v-flex xs12 class="mt-2">
        <v-layout row reverse wrap fill-height justify-center>
          <v-flex xs12 sm4 justify-center d-flex>
            <img src="/digital-campaign.svg" height="200px" alt="Socail">
          </v-flex>
          <v-flex xs12 sm7 justify-center align-center>
            <p class="body-2">{{contactText}}</p>
            <v-spacer></v-spacer>
            <p class="grey--text">{{PSText}}</p>
            <SocialMediaSection :items="contactRecords" />
          </v-flex>
        </v-layout>
      </v-flex>
  </v-layout>
</template>

<script>
import SocialMediaSection from '~/components/SocialMediaSection'
import records from '~/static/records.json'
export default {
  components: {
    SocialMediaSection
  },
  data () {
    const contactText = `If you needed to contact me, just drop me an email or send me a message on
                         Telegram, I'll check them as soon as I can. If you wanted to know more about 
                         me checkout my instagram account, too; I'm quite interested in photography, so 
                         it'll be worth your time, I promise! ;)`
    const PSText = `P.S: I'm not really active on twitter, so ... :D`
    return {
      contactText,
      PSText,
      contactRecords: records.Contact
    }
  }
}
</script>

<style>

</style>
