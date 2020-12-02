<template>
  <div class="home">
    <HelloWorld
        @myProject="$vuetify.goTo('#my-projects')"
        @aboutMe="$vuetify.goTo('#about-me')"
    />
    <section id="my-projects">
<h1 style="text-align: center">הפרוייקטים שלי</h1>
    <Cards :windowInnerWidth="windowInnerWidth"></Cards>
    </section>
    <section id="about-me">
    <parallax :picture="'logo'" :title="'קצת עליי'"></parallax>
    <about-me></about-me>
  </section>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import Cards from "@/components/cards";
import Parallax from "@/components/parallax";
import AboutMe from "@/components/AboutMe";

export default {
  name: 'Home',
  components: {
    AboutMe,
    Parallax,
    Cards,
    HelloWorld
  },
  data:()=>({
    windowInnerWidth: null
  }),
  methods:{
    onResize() {
      this.windowInnerWidth = window.innerWidth
    }
  },
  created() {
    this.windowInnerWidth = window.innerWidth
  },
  mounted() {
    this.$nextTick(() => {
      window.addEventListener('resize', this.onResize);
    })
  },

}
</script>

<!--outlined-->
<!--@click="$vuetify.goTo('#about-me')"-->
<!--&gt;-->
<!--<v-icon>mdi-chevron-double-down</v-icon>-->
<!--</v-btn>-->
<!--</v-row>-->
<!--</v-container>-->
<!--</v-theme-provider>-->
<!--</v-img>-->
<!--</v-row>-->
<!--</section>-->

