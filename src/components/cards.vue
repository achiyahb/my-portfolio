<template>

  <v-container style="display: grid;grid-gap: 1rem;grid-template-columns: repeat(auto-fill,minmax(300px, 1fr));">
    <div

        v-for="(slide, i) in slides"
         :key="i">
      <v-card max height="27rem"
              :class="`rounded-xl`"
              max-width="35rem"
              style="justify-items: stretch"


      >
        <v-img
            src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg"
            height="10rem"

        ></v-img>
        <span
          :color="colors[i]"
          height="100%"
      >{{ slide }}
        </span>
      </v-card>
    </div>
  </v-container>

</template>

<script>
export default {
  name: "carousel",
  data: () => ({
    colors: [
      'indigo',
      'warning',
      'pink darken-2',
      'red lighten-1',
      'deep-purple accent-4',
    ],
    slides: [
      'quiz4fun',
      'mamreemCalculator',
      'achiyaGames',
      'bullShot',
      'rpgecom',
      'myPortfolio'
    ],
  }),
}

</script>
