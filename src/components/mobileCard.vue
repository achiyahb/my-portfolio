<template>
<div>

    <div  v-if="!project.noVideo" style="padding-top: 2rem; text-align: center">
      <iframe :width="250 * 1.33333" height="250"
              :src="`https://www.youtube.com/embed/${project.video}`">
      </iframe>
    </div>
    <div>
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
    <div>
      <div v-if="!project.noVideo" style="padding-top: 0.5rem; text-align: center">
        <v-img width="170"
               style="margin-bottom: 1rem"
               :src="require(`../assets/${project.appPic}`)"
        ></v-img>
      </div>
    </div>

  </div>
</div>
</template>

<script>
import projects from "@/data/projects";

export default {
name: "mobileCard",
  props:['index'],
  data: () => ({
    project: {}
  }),
  created() {
    this.project = projects.getProjectById(this.index)
  },
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
