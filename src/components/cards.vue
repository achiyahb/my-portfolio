<template>
  <v-container
      dir="rtl"
  >
    <section id="cards">
      <div
          style="display: grid;grid-gap: 1rem;grid-template-columns: repeat(auto-fill,minmax(300px, 1fr));">
        <div
            v-for="(card, i) in slides"
            :key="i"
            @click="projectCard(i)"
        >
          <v-card
              :class="`rounded-xl`"
              max-width="35rem"
              style="justify-items: stretch"
              dir="rtl"
              height="250px"
          >
            <v-card-title class="title">
              <p>
                {{ card.title }}
              </p>
            </v-card-title>
            <div style="display: grid;grid-template-columns: 2fr 1fr">
              <div>
                <v-card-subtitle style="padding: 0 1.5rem 0 0">
                  <p class="tab">
                    {{ card.subtitle }}
                  </p>
                </v-card-subtitle>
              </div>
              <div :style="`padding: 0 1rem 1rem 1rem;height: 60px; width: 100px`">
                <div v-for="img of card.pics" style="width: 3rem; justify-items: stretch; justify-content: stretch">
                  <v-img
                      style="margin-bottom: 1rem"
                      :src="require(`../assets/${img}`)"
                  ></v-img>
                </div>
              </div>
            </div>
          </v-card>
        </div>
      </div>
    </section>
    <section id="projectCard">
      <projectCard
          :index="index"
          @close="closeCard"
          v-if="!projectCardOff"
      ></projectCard>
    </section>
  </v-container>
</template>

<script>
import projectCard from "./projectCard"

export default {
  name: "carousel",
  components: {projectCard},
  data: () => ({
    index: null,
    projectCardOff: true,
    colors: [
      'indigo',
      'warning',
      'pink darken-2',
      'red lighten-1',
      'deep-purple accent-4',
    ],
    slides: [
      {
        title: 'quiz4fun',
        pics: ['vue.png', 'firebase.png'],
        subtitle: 'הפרוייקט הראשון שלי \n מורכב משתי אפליקציות מגניבות \n פלטפורמה ליצירת חידונים \n ופלטפורמה להרצת החידונים'
      },
      {
        title: 'Mamreem-Calculator',
        pics: ['firebase.png', 'vuetify.webp'],
        subtitle: 'אפליקציה סופר פרקטית \n מתנת פרידה לחברים מהעבודה הקודמת \n פותרת כאב שהיה לי בתור בעל עסק'
      },
      {
        title: 'Achiya-Games',
        pics: ['js.png', 'vue.png'],
        subtitle: 'המשחקים שלי \n אפליקציה שבניתי בזמני הפנוי \n נטו מתוך תשוקה לאתגר ולקוד'
      },
      {
        title: 'BullShot',
        pics: ['vuex.png', 'firebase.png'],
        subtitle: "אפליקציה עסקית מדהימה \n צללתי לקוד של צוות קודם \n בטכנולוגיה חדשה שלא הכרתי \n הוספתי תיקונים, שיפורים ופיצ'רים"
      },
      {
        title: 'RPGECOM',
        pics: ['nodejs.png', 'rest.jpeg'],
        subtitle: 'אפליקצייה שרובה צד שרת \n מבצעת קריאות לapi של אמזון \n טבילת האש המשמעותית שלי \n בעולם הבקאנד'
      },
      {
        title: 'myPortfolio',
        pics: ['css3.png', 'vuetify.webp'],
        subtitle: 'תיק העבודות שלי \n בוא אתם צופים כעת'
      },
    ],
  }),
  methods: {
    projectCard(i) {
      this.projectCardOff = true

      this.index = i
      this.projectCardOff = false
      this.$vuetify.goTo('#projectCard')
    },
    closeCard() {
      this.$vuetify.goTo('#cards')
      setTimeout(() => {
        this.projectCardOff = true
      }, 50)
    }
  }
}

</script>

<style scoped>
.tab {
  font-size: 1.05rem;
  white-space: pre-wrap;
  justify-content: center;
}

.title {
  justify-content: center;
  margin: 0;
  padding: 1rem 1rem 0.5rem 1rem;
}

.pre-formatted {
  white-space: pre-wrap;
  padding: 1rem;
}

</style>
