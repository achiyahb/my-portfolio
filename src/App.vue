<template>
  <v-app id="inspire">
    <v-app-bar
        app
        clipped-left
    >

      <v-toolbar-title>אחיה חביב</v-toolbar-title>
    </v-app-bar>

    <v-main>
     <router-view/>
    </v-main>

    <v-footer app>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>

</template>

<script>



  export default {
    props: {
      source: String,
    },
    data: () => ({
      drawer: false,
    }),
    created () {
      this.$vuetify.theme.dark = true
    },
  }
</script>
