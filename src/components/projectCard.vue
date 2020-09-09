<template>
  <v-container >

      <v-card dir="rtl" style="display: grid;grid-template-columns: 3fr 2fr">
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
        <v-card-text>
          <p class="pre-formatted">
            {{ project.text }}
          </p>
        </v-card-text>
          <div style="display: grid;grid-template-columns: 3fr 2fr">
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
      </v-card>
  </v-container>
</template>

<script>
export default {
  name: "AboutMe",
  data: () => ({
    project: {
      subtitle: 'אפליקציה ליצירת חידונים',
      title: 'Quiz4Fun',
      text: 'הרעיון נולד מבקשה של יהב בתי בת ה6, לבנות לה אפליקציה ללמוד תנ"ך\n' +
          "זה התחבר לי עם הכובע הקודם שחבשתי,\n" +
          " כבעל עסק המתמקד בחינוך והעשרה " +
          "וכסטודנט לחינוך\n\n" +
          "אהבתי את הרעיון," +
          " אבל החלטתי להפוך אותו לג'נרי \n" +
          "מערכת ליצירת חידונים\n" +
          "בה, כל אחד יוכל להכניס נתונים, ולקבל חידון מגניב\n" +
          "ולשלוח קישור לחברים" ,
      technology: "טכנולוגיות- \n" +
          "הפרוייקט לימד אותי לעבוד עם הפריימוורק vue.js על מנת לבנות את הצד לקוח \n" +
          "עם vuetify על מנת לעצב את האפליקציה לפי העקרונות של material-design\n" +
          "למדתי ויישמתי את המשמעות של כתיבת קוד מודולרי וג'נרי\n" +
          "בדאטה בייס השתמשתי realtime database של firebase\n" +
          "ועל מנת לבצע מניפולציות על הדאטה בצד שרת, השתמשתי בcloud-functions\n" ,
      pics: ['vue.png','vuetify.webp', 'firebase.png'],

    }
  }),
  created() {

  }
}
</script>

<style scoped>
.tab{
  padding: 0 2rem 0 0;
  margin: 0;
}
.pre-formatted {
  white-space: pre-wrap; /* 👈 this is the important part */
  padding: 1rem;
}

</style>
