<template dir="rtl">
  <v-container dir="rtl">
    <v-row class="text-center"

    >
      <v-col cols="12"
             style="padding:0;"
      >
        <v-container  style="padding:0;display: grid;grid-template-columns: 1fr 1fr 1fr;grid-template-rows: 1fr;justify-items: center;align-items: baseline" >
          <div style="grid-column-start: 2;grid-column-end: 3">
            <v-img
                :src="require('../assets/face.jpeg')"
                class="my-3 align-center rounded-circle"
                height="250"
                width="250"
            />
          </div>
        </v-container>
      </v-col>
      <v-col class="mb-4" dir="rtl"  style="padding:0;">
          <h2 >
            שלום!
          </h2>
        <h2 >
          שמי אחיה חביב,
        </h2>
          <h2>
            fullstack developer
          </h2>
        <h1>וברוכים הבאים, לתיק העבודות שלי</h1>
<v-container class="buttons" >
        <v-card style="grid-gap: 2px; grid-column-start: 2;grid-column-end: 3"
                @click="myProjects"
        >
        <v-card-text >הפרוייקטים שלי</v-card-text>
          </v-card>
  <v-card style=" grid-gap: 40px; grid-column-start: 2;grid-column-end: 3; grid-row-start: 3"
  @click="aboutMe"
  >
        <v-card-text
        >קצת עליי</v-card-text>
        </v-card>
</v-container>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
  export default {
    name: 'HelloWorld',

    data: () => ({

    }),
    methods: {
      myProjects(){
          this.$emit('myProject', 'click')
      },
      aboutMe(){
        this.$emit('aboutMe', 'click')
      }
    }
  }
</script>

<style>
  .buttons{
    display: grid;
    grid-template-columns: 1fr 2fr 1fr;grid-template-rows: 3rem 1rem  3rem;
  }
</style>
