<template>
  <v-app id="inspire">
    <v-app-bar
        app
        clipped-left
    >

      <v-toolbar-title>achiya haviv</v-toolbar-title>
      <v-spacer></v-spacer>
      <div v-for="icon of icons" style="padding-left: 4px">
        <a :href="`${icon.link}`">
        <v-icon
            :class="`${icon.class}`"
        ></v-icon>
        </a>

      </div>

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
      icons: [
        {class:'fab fa-facebook-square',link:'https://www.facebook.com/profile.php?id=100013305678737'},
        {class:'fab fa-linkedin',link:'https://www.linkedin.com/in/achiya-haviv/'}
      ]
    }),
    created () {
      this.$vuetify.theme.dark = true
    },
  }
</script>

<style>
a {
  text-decoration-line: none;
}
</style>
