<template>
    <v-layout row wrap>
      <v-btn v-for="item in items" class="" v-if="item.type !== 'phone'" :key="item.id" :href="item.url" target="_blank" icon>
        <v-avatar tile size="25">
          <img :src="item.icon" :alt="item.title">
        </v-avatar>
      </v-btn>
      <v-flex xs12>
        <div class="heading mt-2 mb-2">Phone Numbers</div>
        <v-divider></v-divider>
        <v-card class="pa-2 mt-2 tell-card" v-for="item in items" v-if="item.type === 'phone'" :key="item.id">
          <v-layout row >
            <v-flex xs12 sm2 d-flex justify-center align-center>
              <v-avatar tile size="25">
                <img :src="item.icon" :alt="item.title">
              </v-avatar>
            </v-flex>
            <v-flex xs12 sm10>
              <div class="subheading">{{item.title}}</div>
              <div v-if="!item.hidden" class="body-2">{{item.value}}</div>
              <div v-else class="body-2"><a :href="item.url">Request Info</a></div>
            </v-flex>
          </v-layout>
        </v-card>
      </v-flex>
    </v-layout>
</template>

<script>
export default {
  props: {
    items: Array
  }
}
</script>

<style scoped>
  .tell-card {
    max-width: 300px;
  }
</style>
