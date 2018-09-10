<template>
    <v-layout :id="String(id)" row reverse wrap class="my-2 elevation-1">
      <v-flex xs12 sm4>
        <v-layout row wrap justify-center align-center fill-height>
          <v-flex xs12 justify-center align-center d-flex>
            <v-layout fill-height justify-center wrap>
              <v-flex xs12 justify-center align-center d-flex>
                <img :src="image" height="100px" :alt="title"/>
              </v-flex>
              <v-flex xs12 justify-center d-flex class="px-2 my-3">
                <div class="title text-xs-center font-weight-thin">
                  {{title}}
                </div>
              </v-flex>
            </v-layout>
          </v-flex>
        </v-layout>
      </v-flex>
      <v-flex xs12 sm8>
        <v-list two-line subheader>
          <v-list-tile v-for="skill in skills" :key="skill.id" avatar @click="() => openDialog(skill)">
            <v-list-tile-avatar tile>
              <img :src="skill.logo" height="60px" :alt="skill.title">
            </v-list-tile-avatar>

            <v-list-tile-content>
              <v-list-tile-title>{{ skill.title }}</v-list-tile-title>
              <v-list-tile-sub-title>{{ skill.expertise + " - " + skill.duration}}</v-list-tile-sub-title>
            </v-list-tile-content>

            <v-list-tile-action>
              <v-btn @click="openDialog" icon ripple>
                <v-icon color="grey lighten-1">info</v-icon>
              </v-btn>
            </v-list-tile-action>
          </v-list-tile>
        </v-list>
      </v-flex>
      <v-dialog
        v-model="isOpen"
        max-width="400"
      >
        <v-card>
          <v-card-title primary-title>
            <div>
              <div class="font-weight-thin headline">{{selectedSkill.title}}</div>
              <span class="gray--text">{{ selectedSkill.expertise + " - " + selectedSkill.duration}}</span>
            </div>
          </v-card-title>
          <v-card-text>
            {{selectedSkill.description}}
          </v-card-text>
        </v-card>
      </v-dialog>
    </v-layout>
</template>

<script>
export default {
  props: {
    skills: Array,
    image: String,
    title: String,
    id: Number
  },
  data () {
    return {
      isOpen: false,
      selectedSkill: {}
    }
  },
  methods: {
    openDialog: function (skill) {
      this.selectedSkill = skill
      this.isOpen = true
    }
  }
}
</script>

<style>

</style>
