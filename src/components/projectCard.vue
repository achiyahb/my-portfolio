<template>
  <v-container >
    <v-card dir="rtl" >
        <v-row>
          <v-spacer></v-spacer>
          <a style="cursor: pointer">
              <v-icon
                  class="fas fa-times ml-8 mt-2"
                  @click="closeCard"
              ></v-icon>
          </a>
        </v-row>
        <div :style="`${windowInnerWidth < 700 ?'':`display: grid; ${!project.noVideo  ? 'grid-template-columns:3fr 2fr':''}`}`">
        <div id="text_content" >
          <v-card-title>
          <p  class="tab">
            {{ project.title }}
          </p>
        </v-card-title>
        <v-card-subtitle>
          <p  class="tab">
            {{ project.subtitle }}
          </p>
        </v-card-subtitle>
          <div :style="`display: grid; ${!project.noVideo  ? '':'grid-template-columns: repeat(auto-fill,minmax(300px, 1fr))'}`">
          <v-card-text style="padding-top: 0">
          <p class="pre-formatted" style="padding-top: 0">
            {{ project.text }}
          </p>
        </v-card-text>

          <div style="display: grid;grid-template-columns: 3fr 1fr"
               :class="{one: project.noVideo}"
          >
            <div>
              <v-card-text style="padding-top: 0">
                <p class="pre-formatted" style="padding-top: 0">
                  {{ project.technology }}
                </p>
              </v-card-text>
            </div>
            <div style=" padding: 1rem 1rem 1rem 1rem;height: 60px; width: 100px">
              <div v-for="img of project.pics" style="width: 3rem; justify-items: stretch; justify-content: stretch">
                <v-img
                    style="margin-bottom: 1rem"
                    :src="require(`../assets/${img}`)"
                ></v-img>
              </div>
            </div>
          </div>
          </div>
        </div>
          <div v-if="!project.noVideo">
            <div :style="`${windowInnerWidth < 700 ?'':'padding-top: 4rem'}`">
              <iframe width="266.666666" height="200"
                      :src="`https://www.youtube.com/embed/${project.video}`">
              </iframe>
            </div>
            <div style="padding-top: 1rem">
                <v-img width="170"
                       style="margin-bottom: 1rem"
                       :src="require(`../assets/${project.appPic}`)"
                ></v-img>
            </div>
          </div>
        </div>
      </v-card>
  </v-container>
</template>

<script>
import projects from "@/data/projects";

export default {
  name: "AboutMe",
  props: ['index','windowInnerWidth'],
  data: () => ({
    project: {}
  }),
  methods:{
    closeCard(){
      this.$emit('close', 'click')
    }
  },
  watch:{
    index(){
      this.project = projects.getProjectById(this.index)
    },
  },
  created() {
    this.project = projects.getProjectById(this.index)
  }
}
</script>

<style scoped>
.tab{
  padding: 0 2rem 0 0;
  white-space: pre-wrap;
  margin: 0;
}
.pre-formatted {
  white-space: pre-wrap; /* 👈 this is the important part */
  padding: 1rem;
}
@media only screen and (max-width: 1050px) {
  .one{
    display: none;
  }
}
</style>
