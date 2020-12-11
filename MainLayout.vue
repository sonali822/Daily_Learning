<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
  <q-btn v-if="$route.fullPath.includes('/chat')" v-go-back.single flat dense  icon="arrow_back" label="On Left" />
        <q-toolbar-title class="absolute-center">
          {{ title }}
        </q-toolbar-title>

        </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { openURL } from 'quasar'

export default {
  computed: {
    title () {
      return console.log(this.$route)
      // const currentPath = this.$route.fullPath
      // if (currentPath === '/') return 'SmakChat'
      // else if (currentPath === '/chat') return 'Chat'
      // else if (currentPath === '/auth') return 'Login'
    }
  },
  methods: {
    openURL
  }
}
</script>

<style>
</style>
