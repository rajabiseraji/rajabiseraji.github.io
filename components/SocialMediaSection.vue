<template>
    <v-layout row wrap>
      <v-btn v-for="item in items" class="pa-3" :key="item.id" :href="item.url" target="_blank" icon>
        <v-avatar tile size="30">
          <img :src="item.icon" :alt="item.title">
        </v-avatar>
      </v-btn>
    </v-layout>
</template>

<script>
export default {
  props: {
    items: Array
  }
}
</script>

<style>

</style>
